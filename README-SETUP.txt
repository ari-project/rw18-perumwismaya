SETUP PORTAL RW 18 + FIREBASE

1. Upload seluruh file website ke hosting.
   - index.html
   - firebase-config.js
   - firestore.rules (untuk konfigurasi Firestore, bukan file yang diupload ke web)

2. Konfigurasi Firebase Web App yang sudah dimasukkan:
   Project ID: rw18-perum-wismajaya
   Auth Domain: rw18-perum-wismajaya.firebaseapp.com

3. Di Firebase Console:
   Authentication -> Sign-in method -> aktifkan Email/Password.

4. Buat akun admin/bendahara:
   Authentication -> Users -> Add user.
   Contoh:
   email: bendahara@rw18.local
   password: buat password sendiri yang kuat.

5. Firestore Database:
   Buat database Firestore, kemudian pasang rules dari file firestore.rules.

6. Jalankan website melalui HTTP/HTTPS hosting.
   Jangan membuka index.html langsung dengan file:// karena module JavaScript Firebase bisa diblokir browser.

CATATAN KEAMANAN:
Konfigurasi Firebase Web termasuk apiKey memang digunakan oleh aplikasi web. Keamanan utama tetap berasal dari Authentication dan Firestore Security Rules. Jangan menaruh password admin/bendahara di dalam HTML atau JavaScript.
