# SisaBaik
Developed by qiya

SisaBaik adalah proyek berkembang pada mata kuliah Pengembangan Web. Aplikasi ini dirancang untuk membantu penyedia memulihkan nilai stok makanan berlebih melalui penjualan dengan harga khusus atau penyaluran, sekaligus membantu masyarakat memperoleh makanan yang lebih terjangkau dan mengurangi limbah pangan.

## Capaian Chapter 2

* Membuat halaman informasi SisaBaik dengan semantic HTML.
* Membuat formulir pendaftaran penyedia yang aksesibel.
* Membuat formulir penawaran makanan berlebih yang aksesibel.
* Mengelola perubahan kode dengan Git dan GitHub.

## Halaman

* `index.html`: halaman informasi SisaBaik.
* `daftar-penyedia.html`: formulir pendaftaran penyedia.
* `tawarkan-makanan.html`: formulir penawaran makanan berlebih.

## Menjalankan proyek

Buka folder proyek di Visual Studio Code, lalu tampilkan `index.html` menggunakan Live Preview atau browser. Pada tahap ini, formulir hanya merupakan prototipe HTML: data belum disimpan ke server atau basis data.

## Integritas akademik

Pengerjaan proyek berkembang mengikuti kebijakan mata kuliah. AI generatif tidak diperkenankan pada tahap ini. Mahasiswa wajib mampu menjelaskan setiap elemen dan atribut yang digunakan.


# SisaBaik
SisaBaik adalah proyek berkembang pada mata kuliah Pengembangan Web. Aplikasi ini dirancang untuk membantu penyedia memulihkan nilai stok makanan berlebih melalui penjualan dengan harga khusus atau penyaluran, sekaligus membantu masyarakat memperoleh makanan yang lebih terjangkau dan mengurangi limbah pangan.

## Capaian Chapter 3
- Mempertahankan semantic HTML dan formulir aksesibel dari Chapter 2.
- Menerapkan CSS cascade, box model, dan custom properties.
- Menggunakan Flexbox untuk navigasi dan kelompok tombol.
- Menggunakan Grid untuk kartu penawaran dan bagian halaman.
- Membangun layout mobile-first dengan media queries.
- Memeriksa kontras, fokus keyboard, reflow, dan konsistensi visual.

## Halaman
- index.html: halaman informasi SisaBaik.
- daftar-penyedia.html: formulir pendaftaran penyedia.
- tawarkan-makanan.html: formulir penawaran makanan berlebih.
- styles.css: sistem visual dan layout responsif untuk seluruh halaman.

## Menjalankan proyek
Buka folder proyek di Visual Studio Code, lalu tampilkan index.html menggunakan Live Preview atau browser. Pada tahap ini, formulir hanya merupakan prototipe HTML: data belum disimpan ke server atau basis data.

## Integritas akademik
Pengerjaan proyek berkembang mengikuti kebijakan mata kuliah. AI generatif tidak diperkenankan pada tahap ini. Mahasiswa wajib mampu menjelaskan setiap elemen dan atribut yang digunakan.

# Capaian Chapter 7
1. Membuat REST API untuk SisaBaik.
2. Menghubungkan API dengan database PostgreSQL.
3. Membuat fitur pemesanan makanan.
4. Menambahkan validasi request dan penanganan error.
5. Melakukan pengujian API dan database.

# Dokumentasi

docs/API.md: dokumentasi API.

docs/hasil-uji-chapter7.md: hasil pengujian.

# Menjalankan API

Jalankan server menggunakan perintah yang tersedia pada proyek. Pengujian API dapat dijalankan dengan npm run api:test.

Pengujian konkurensi dapat dijalankan dengan node scripts/uji-konkurensi.js.


# Autentikasi dan Otorisasi
# Persiapan

Pastikan Node.js, npm, dan PostgreSQL sudah tersedia.

Konfigurasikan variabel lingkungan lokal di file .env berdasarkan kebutuhan aplikasi.

Jalankan migrasi autentikasi database/07_auth.sql pada database pengembangan yang sesuai.

Jalankan server dengan npm run dev.

# Pengujian

Jalankan pengujian autentikasi menggunakan:

npm run auth:test

Pengujian ini menjalankan rangkaian pemeriksaan autentikasi dan akses data. Pastikan database pengembangan telah dikonfigurasi dengan benar sebelum menjalankannya.

# Registrasi dan akses

Aplikasi mendukung akun pembeli dan penyedia. Akses penyedia mengikuti mekanisme verifikasi yang diterapkan aplikasi. Endpoint yang memerlukan autentikasi harus menggunakan token yang valid, sedangkan endpoint khusus penyedia juga memerlukan peran dan status verifikasi yang sesuai.

# Keamanan

Simpan kredensial dan rahasia hanya di .env lokal.

Jangan masukkan .env, kata sandi, atau token ke Git.

Logout digunakan untuk mencabut sesi sesuai mekanisme autentikasi aplikasi.

Lihat docs/API.md untuk rincian endpoint, format request, dan respons API.

## Chapter 9 — Frontend Vue SisaBaik

### Teknologi
- Node.js: v24.21.0
- npm: v11.19.0
- Vue: 3.5.43
- Vite: 8.3.3

### Menjalankan frontend

Masuk ke folder frontend:

# bash
cd frontend
npm install
npm run dev

Aplikasi development berjalan di:
http://127.0.0.1:5173/

### Build dan preview

# bash
npm run build
npm run preview

Preview berjalan di:
http://127.0.0.1:4173/

### Struktur frontend
- src/assets: logo dan ilustrasi SVG.
- src/components: komponen Vue.
- src/data: data fixture latihan.
- src/lib: fungsi utilitas dan visual.

### Catatan
Frontend Chapter 9 menggunakan data fixture di memori browser.
Perubahan data latihan tidak disimpan secara permanen dan akan
kembali ke data awal setelah halaman di-refresh.

Pada Chapter 9, frontend masih menggunakan data fixture di memori browser. Integrasi dengan backend Express dan PostgreSQL melalui REST API dilakukan pada Chapter 10.

## Chapter 10 — Integrasi Full Stack SisaBaik dengan Vue dan REST API

### 1. Fitur dan Alur Sistem

#### A. Manajemen Pengguna
•	Registrasi akun pembeli dan penyedia.
•	Login dan logout menggunakan mekanisme autentikasi.
•	Pengelolaan profil penyedia.
•	Verifikasi penyedia sebelum memperoleh akses pengelolaan penawaran.
#### B. Manajemen Penawaran
•	Penyedia dapat membuat, melihat, dan mengubah penawaran.
•	Penawaran memiliki informasi nama, kategori, harga normal, harga penawaran, stok, satuan, masa berlaku, status, dan foto.
•	Foto penawaran divalidasi berdasarkan tipe dan ukuran file, kemudian diproses menjadi format WebP.
•	Pengelolaan penawaran memperhatikan versi data untuk mencegah perubahan stok berdasarkan informasi yang sudah tidak terbaru.
#### C. Katalog Penawaran
•	Pembeli dapat melihat penawaran yang tersedia.
•	Pencarian dan filter kategori dilakukan melalui API.
•	Katalog menerapkan pagination untuk membatasi jumlah data yang ditampilkan.
•	Penawaran yang tidak memenuhi ketentuan publikasi tidak ditampilkan pada katalog publik.
#### D. Pemesanan dan Pengelolaan Transaksi
Alur transaksi melibatkan pembeli dan penyedia melalui tahapan berikut:
1.	Pembeli memilih penawaran dan menentukan kuantitas.
2.	Sistem memvalidasi ketersediaan stok dan membuat pesanan.
3.	Stok direservasi ketika pesanan berhasil dibuat.
4.	Penyedia dapat mengonfirmasi atau menolak pesanan.
5.	Pesanan yang dikonfirmasi dapat diproses hingga siap diambil.
6.	Pembayaran dan pengambilan dicatat ketika proses serah terima diselesaikan.
7.	Pesanan yang dibatalkan atau ditolak memulihkan stok sesuai aturan transaksi.
#### E. Dashboard
Dashboard menyajikan indikator berdasarkan data transaksi sesuai cakupan akun dan status transaksi, antara lain:
•	Ringkasan jumlah pesanan.
•	Nilai transaksi dan pendapatan.
•	Informasi stok dan penawaran.
•	Indikator transaksi selesai, dibatalkan, dan pengambilan.
2. Aturan Bisnis dan Pengelolaan Data
Beberapa aturan utama yang diterapkan dalam sistem:
•	Harga dan total transaksi dihitung oleh server, bukan ditentukan oleh browser.
•	Stok yang ditampilkan pada pengelolaan penawaran merupakan stok yang masih tersedia setelah memperhitungkan reservasi.
•	Reservasi stok tidak langsung dihitung sebagai pendapatan.
•	Pembatalan dan penolakan pesanan memulihkan stok sesuai kondisi transaksi.
•	Pembayaran dan pengambilan dicatat berdasarkan penyelesaian serah terima.
•	Pesanan gratis tidak menghasilkan pendapatan.
•	Perubahan penawaran menggunakan informasi versi terbaru untuk menghindari konflik perubahan data.
•	Akses data dibatasi berdasarkan autentikasi, peran pengguna, status verifikasi, dan kepemilikan data.
3. Pengujian Sistem
Pengujian dilakukan untuk memeriksa integrasi frontend, backend, database, serta aturan bisnis transaksi.
Pengujian otomatis alur transaksi dapat dijalankan melalui:
npm run workflow:test
Pengujian otomatis dilakukan untuk memeriksa aturan bisnis dan alur transaksi pada backend. Sebanyak 26 skenario pengujian alur transaksi telah lulus:
 Pengujian mencakup pengelolaan stok, pemesanan, pembatalan, pembayaran, pengambilan, validasi foto, konflik perubahan data, dan perhitungan dashboard.
Pengujian manual melalui browser dilakukan secara terpisah untuk memeriksa tampilan, navigasi, interaksi formulir, respons API, serta kondisi aplikasi ketika terjadi gangguan koneksi.
4. Batasan Sistem
Pada tahap pengembangan ini, aplikasi masih memiliki beberapa batasan:
•	Sesi autentikasi disimpan di memori aplikasi browser sehingga pengguna perlu login kembali setelah halaman di-refresh.
•	Pembayaran dilakukan di luar payment gateway; sistem mencatat pembayaran yang diterima saat serah terima.
•	Fitur reset kata sandi dan verifikasi email belum tersedia.
•	Idempotency key untuk pengamanan request berulang belum diterapkan.
•	Pembaruan data secara realtime belum tersedia.
•	Perhitungan penghematan biaya penjual belum diimplementasikan.
5. Keamanan dan Konfigurasi
•	Konfigurasi database dan kredensial disimpan dalam file .env lokal.
•	File .env tidak boleh dimasukkan ke repository Git.
•	Endpoint yang memerlukan autentikasi harus menggunakan token yang valid.
•	Hak akses ditentukan melalui peran, status verifikasi, dan kepemilikan data.
•	Validasi input dan aturan transaksi dilakukan pada sisi server.