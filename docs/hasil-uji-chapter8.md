# Hasil Pengujian Chapter 8 — SisaBaik

1. Lingkungan Pengujian

Proyek: SisaBaik API

Branch: feature/auth-rbac

Database: sisabaik_dev

Server lokal: http://127.0.0.1:3000

Akun pengujian: Rina Baru, Budi Baru, Siti Baru, dan Andi Baru

2. Hasil Pengujian yang Terverifikasi

2.1 Pengujian Otomatis Autentikasi

Skenario: Menjalankan pengujian otomatis autentikasi.

Hasil: 44 pemeriksaan HTTP dan assertion dinyatakan lulus.

Status: Lulus.

2.2 Akses Profil Pengguna dengan Token Valid

Endpoint: GET /api/auth/saya

Hasil: Server memberikan respons HTTP 200.

Status: Lulus.

2.3 Akses Profil Tanpa Token

Endpoint: GET /api/auth/saya

Hasil: Server memberikan respons HTTP 401 karena token tidak disertakan.

Status: Lulus.

2.4 Penggunaan Token Kedaluwarsa

Hasil: Server memberikan respons HTTP 401 dengan kode TOKEN_EXPIRED.

Status: Lulus.

2.5 Pembeli Mencoba Membuat Penawaran

Hasil: Server menolak permintaan dengan respons HTTP 403.

Status: Lulus.

2.6 Penyedia Mencoba Membuat Pesanan

Hasil: Server memberikan respons HTTP 403 dengan kode ROLE_FORBIDDEN.

Status: Lulus.

2.7 Pemeriksaan Database Penawaran dan Stok

Pengujian: Menjalankan query untuk memeriksa data penawaran dan stok.

Hasil: Data penawaran dan jumlah stok berhasil ditampilkan.

Status: Berhasil.

2.8 Pemeriksaan Database Pesanan dan Detail Transaksi

Pengujian: Menjalankan query untuk memeriksa data pesanan dan detail transaksi.

Hasil: Data pesanan dan detail transaksi berhasil ditampilkan. Salah satu data yang ditemukan adalah pesanan ID 7 milik akun siti.baru@example.test dengan total transaksi Rp6.000.

Status: Berhasil.

2.9 Pemeriksaan Pesanan Antar Pengguna

Pengujian: Memeriksa daftar pesanan menggunakan akun pengguna yang berbeda.

Hasil: Pesanan milik pengguna lain tidak ditampilkan pada halaman aplikasi.

Status: Lulus untuk pemeriksaan tampilan.

3. Pengujian yang Belum Terverifikasi

Pengujian berikut belum memiliki bukti yang cukup untuk dinyatakan lulus:

Memastikan token lama ditolak setelah logout dengan kode SESSION_REVOKED.

Memastikan login ditolak ketika akun dinonaktifkan.

Memastikan pembatasan percobaan login dan registrasi berfungsi sesuai konfigurasi.

Memastikan akses terhadap data pengguna lain menghasilkan status HTTP yang sesuai pada endpoint terkait.

Memastikan permintaan yang tidak berwenang tidak mengubah data maupun metadata database.

Melakukan pengujian konkurensi pemesanan ketika stok tersisa satu unit.

4. Catatan Keamanan

Token JWT dan kata sandi tidak dicantumkan dalam laporan.

Nilai rahasia dari file .env tidak dimasukkan ke dalam dokumentasi.

Pengujian yang belum terverifikasi tidak dinyatakan lulus.

5. Kesimpulan

Pengujian otomatis autentikasi telah menghasilkan 44 pemeriksaan yang lulus. Sejumlah pengujian manual juga berhasil memverifikasi autentikasi, pembatasan akses berdasarkan peran, serta pemeriksaan data penawaran dan pesanan. Beberapa pengujian keamanan tambahan masih perlu diverifikasi sebelum seluruh rangkaian pengujian Chapter 8 dinyatakan selesai.