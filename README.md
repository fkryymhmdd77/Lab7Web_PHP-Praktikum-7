# Lab7Web_PHP-Praktikum-7

## Tujuan
Memahami pemrograman server-side dengan PHP, variabel, operator, percabangan, perulangan, array, function, pemrosesan form GET/POST, validasi, sanitasi, dan pengolahan data sederhana.

## Perangkat
- Laptop/PC dan web browser
- Visual Studio Code atau editor teks
- PHP dan web server lokal melalui XAMPP atau Laragon

## Cara menjalankan
1. Jalankan Apache dari XAMPP (atau web server dari Laragon).
2. Salin folder `Lab7Web_PHP` ke `C:\\xampp\\htdocs\\` jika menggunakan XAMPP.
3. Buka browser ke `http://localhost/Lab7Web_PHP/`.
4. Pilih latihan melalui halaman menu `index.php`.

Jangan menjalankan file PHP dengan klik ganda; akses melalui `localhost`.

## Struktur file
- `index.php`: halaman menu.
- `latihan1.php`: menjalankan PHP dan menampilkan waktu server.
- `latihan2.php`: variabel, operator, nilai akhir, dan predikat.
- `latihan3.php`: array dan `foreach` dengan tujuh nama mahasiswa.
- `latihan4.php`: function diskon, luas persegi panjang, dan format Rupiah.
- `latihan5.php`: pemrosesan GET dan pencarian nama dalam array.
- `latihan6.php`: pemrosesan form POST nama dan program studi.
- `latihan7.php`: validasi transaksi dan perhitungan subtotal.
- `mini_project.php`: formulir data mahasiswa dengan validasi server-side.

## Ringkasan hasil
Semua latihan dibuat dalam file terpisah. Input form diproses di sisi server. Output yang berasal dari input pengguna ditampilkan menggunakan `htmlspecialchars()` untuk mengurangi risiko injeksi HTML/script. Mini project memvalidasi kolom wajib, NIM 10 digit, semester bilangan bulat 1–14, serta format email.

## Pengujian input
**Kasus valid:**
1. Mini project: nama `Andi`, NIM `1234567890`, prodi `Teknik Informatika`, semester `3`, email `andi@example.com` — data diterima.
2. Transaksi: barang `Buku`, harga `15000`, jumlah `2` — subtotal `Rp30.000`.

**Kasus tidak valid:**
1. Mini project: NIM `12345` — ditolak karena bukan 10 digit.
2. Mini project: semester `15` atau email `andi@` — ditolak karena semester di luar rentang atau format email tidak valid.
3. Transaksi: jumlah `0` atau `-2` — ditolak karena jumlah minimal 1 dan harus bilangan bulat.

## Eksperimen mandiri
1. Nilai rata-rata tiga komponen dapat dihitung dengan `(tugas + uts + uas) / 3`. Pada latihan 2 digunakan bobot tugas 30%, UTS 30%, dan UAS 40% sesuai contoh modul.
2. Latihan GET mencari nama dengan `stripos()` sehingga pencarian tidak membedakan huruf besar/kecil.
3. Function `formatRupiah()` menggunakan `number_format($angka, 0, ",", ".")`.
4. NIM divalidasi dengan `ctype_digit()` dan `strlen($nim) === 10`; panjang 10 digit merupakan ketentuan yang ditetapkan untuk contoh ini.
5. Tombol reset membersihkan nilai input di browser. Reset tidak menghapus atau mengubah data di server dan tidak menggantikan validasi/pemrosesan ulang server.

## Jawaban pertanyaan evaluasi
1. **Client-side** berjalan di browser pengguna, misalnya HTML, CSS, dan JavaScript. **Server-side** berjalan di server untuk menerima permintaan, memproses input/aturan aplikasi, lalu mengirim respons ke browser.
2. File PHP harus melalui web server karena kode PHP diproses di sisi server. Browser menerima hasil output seperti HTML, bukan kode PHP mentah.
3. Tanda `$` digunakan sebagai awalan nama variabel PHP, misalnya `$nama`.
4. GET mengirim data melalui parameter URL dan cocok untuk permintaan yang tidak mengubah data. POST mengirim data pada body permintaan dan lazim digunakan untuk pengiriman form. POST bukan enkripsi; gunakan HTTPS untuk melindungi data saat dikirim.
5. Validasi server-side diperlukan karena validasi HTML/browser dapat dilewati atau dimanipulasi. Server harus memastikan data sesuai aturan sebelum diproses.
6. `htmlspecialchars()` mengubah karakter khusus HTML menjadi bentuk aman saat ditampilkan, sehingga membantu mengurangi risiko injeksi HTML/script.
7. Function membuat kode dapat digunakan kembali, mengurangi pengulangan, membuat program lebih terstruktur, dan memudahkan pemeliharaan/pengujian.
