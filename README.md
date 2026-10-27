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