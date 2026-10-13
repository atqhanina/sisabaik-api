# Hasil Pengujian Chapter 7

# Pengujian API
Pengujian API dijalankan menggunakan perintah npm run api:test. Hasil pengujian menunjukkan bahwa seluruh pengujian otomatis berhasil dijalankan.

# Pengujian Validasi Request
Pengujian dilakukan menggunakan Console browser. JSON yang tidak valid menghasilkan status HTTP 400, request dengan Content-Type yang tidak sesuai menghasilkan HTTP 415, dan request dengan ukuran body yang melebihi batas menghasilkan HTTP 413.

# Pengujian Pemesanan
Pemesanan berhasil dibuat dengan status HTTP 201. Data pesanan dan detailnya tersimpan di database PostgreSQL. Setelah server dijalankan ulang, detail pesanan dengan ID 4 masih dapat diakses melalui endpoint /api/pesanan/4.

# Pengujian Konkurensi
Pengujian dijalankan menggunakan perintah node scripts/uji-konkurensi.js. Hasilnya menunjukkan satu permintaan berhasil dan satu permintaan ditolak, dengan stok akhir 0.