RW 18 PERUM WISMAJAYA - SETUP DATABASE ONLINE

1. Buat project Firebase
   - Buka Firebase Console: https://console.firebase.google.com/
   - Create project baru.
   - Tambahkan Web App.

2. Aktifkan Authentication
   - Authentication -> Sign-in method
   - Aktifkan Email/Password.
   - Buat user admin/bendahara dari Firebase Console.

3. Aktifkan Firestore Database
   - Firestore Database -> Create database.
   - Pilih mode production.

4. Masukkan Firestore Rules
   - Buka Firestore Database -> Rules.
   - Salin isi file firestore.rules ke editor Rules.
   - Publish.

5. Pasang Firebase Config
   - Dari Project settings -> Your apps -> SDK setup/configuration.
   - Salin konfigurasi firebaseConfig.
   - Buka index.html.
   - Cari blok:
       const firebaseConfig = { ... };
   - Ganti nilai GANTI_API_KEY, GANTI_PROJECT, dll dengan nilai asli.

6. Jalankan website
   - Untuk tes cepat, gunakan hosting lokal/static server.
   - Jangan membuka file HTML via file:/// apabila browser memblokir modul atau Firebase.

7. Struktur koleksi yang digunakan
   settings/finance
     openingBalance: number
     updatedAt: timestamp
     updatedBy: string

   transactions/{autoId}
     date: YYYY-MM-DD
     type: income | expense
     category: string
     description: string
     amount: number
     createdBy: string
     createdAt: timestamp

CATATAN KEAMANAN
- Data transaksi dapat dibaca publik karena portal memang menampilkan transparansi keuangan.
- Hanya akun Firebase yang sudah login yang dapat menambah/menghapus transaksi berdasarkan Rules di atas.
- Untuk produksi yang lebih ketat, sebaiknya Rules membatasi penulisan berdasarkan custom claims role=admin/bendahara, bukan sekadar user login.
