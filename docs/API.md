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