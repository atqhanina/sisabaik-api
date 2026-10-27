# Dokumentasi REST API SisaBaik
SisaBaik merupakan aplikasi yang dikembangkan untuk membantu mengurangi limbah makanan dengan menyediakan penawaran makanan berlebih. Pada Chapter 7, proyek ini dikembangkan dengan REST API yang terhubung ke database PostgreSQL untuk mendukung pengelolaan penawaran dan pemesanan.

# Alamat API

API dijalankan secara lokal melalui alamat http://127.0.0.1:3000. Alamat ini digunakan selama pengembangan dan pengujian di komputer lokal.

# Daftar Penawaran

Endpoint GET /api/penawaran digunakan untuk mengambil data penawaran makanan yang tersedia. Data ini digunakan oleh halaman aplikasi untuk menampilkan informasi penawaran kepada pengguna.

# Membuat Pesanan
Endpoint POST /api/pesanan digunakan untuk membuat pesanan berdasarkan data yang dikirim melalui request body dalam format JSON. Request harus menggunakan Content-Type: application/json. Data pesanan diproses dan disimpan ke database apabila memenuhi validasi yang diterapkan oleh aplikasi.

# Melihat Detail Pesanan
Endpoint GET /api/pesanan/:id digunakan untuk mengambil detail pesanan berdasarkan ID. Informasi yang dikembalikan mencakup data pesanan dan item yang terkait dengan pesanan tersebut.

# Penanganan Kesalahan
API menggunakan status HTTP untuk menunjukkan hasil pemrosesan request. Status 201 menunjukkan bahwa pesanan berhasil dibuat, status 400 menunjukkan request tidak valid, status 413 menunjukkan ukuran request body melebihi batas, dan status 415 menunjukkan bahwa request tidak menggunakan format JSON yang diwajibkan.

# Pengujian
Pengujian API otomatis dijalankan menggunakan perintah npm run api:test. Pengujian konkurensi dijalankan menggunakan perintah node scripts/uji-konkurensi.js. Kedua pengujian digunakan untuk memeriksa perilaku API sesuai skenario yang telah disiapkan.


# Autentikasi dan Otorisasi
# Registrasi dan sesi

API autentikasi menggunakan prefix /api/auth. Endpoint registrasi, login, profil pengguna, dan logout mengikuti implementasi pada src/routes/auth.js.

Gunakan format request dan field yang didefinisikan oleh implementasi aktual. Jangan mengirimkan kata sandi atau token ke log maupun dokumentasi.

# Akses berdasarkan peran

Endpoint khusus pembeli hanya dapat diakses oleh peran yang diizinkan.

Endpoint pengelolaan penawaran dibatasi untuk penyedia yang memenuhi persyaratan verifikasi dan kepemilikan.

Endpoint pesanan harus membatasi data sesuai identitas pengguna yang terautentikasi.

Identitas pengguna tidak boleh dipercaya hanya karena dikirim melalui body request.

# Respons kesalahan
Respons autentikasi dan otorisasi dapat mencakup:
# HTTP & Keterangan

401: Token tidak tersedia, tidak valid, atau kedaluwarsa; atau kredensial login ditolak

403: Peran atau status akun tidak memenuhi persyaratan akses

404: Data tidak ditemukan atau tidak tersedia bagi pengguna yang meminta

429: Batas permintaan terlampaui, jika rate limit berlaku

Kode kesalahan spesifik mengikuti implementasi API.

# Kebijakan data

Katalog publik hanya boleh menampilkan penawaran yang memenuhi ketentuan publikasi aplikasi. Data pesanan dan detail transaksi harus dibatasi sesuai kepemilikan. Harga transaksi perlu mempertahankan snapshot yang digunakan ketika pesanan dibuat.

# Pengujian

Hasil pengujian Chapter 8 dicatat dalam docs/hasil-uji-chapter8.md. Hasil yang belum terverifikasi harus tetap ditandai sebagai belum diuji.