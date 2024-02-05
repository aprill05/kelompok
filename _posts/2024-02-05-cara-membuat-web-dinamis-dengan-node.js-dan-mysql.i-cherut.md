---
layout: post
title:  "cara membuat web dinamis dengan node.js dan mysql.i cherut"
date:   2024-02-05 13:28:55 +0800
categories: jekyll update
---

Untuk membuat web dinamis dengan Node.js dan MySQL, Anda dapat mengikuti langkah-langkah dasar berikut:

Persiapkan Lingkungan:
Pastikan Anda telah menginstal Node.js di sistem Anda. Anda dapat mengunduhnya dari situs resmi Node.js. Instal MySQL dan pastikan server MySQL berjalan.

Inisialisasi Proyek Node.js:
Buat direktori proyek baru dan masuk ke dalamnya melalui terminal. Jalankan perintah npm init untuk membuat berkas package.json dan ikuti petunjuk untuk mengisi informasi proyek.

Pasang Modul yang Dibutuhkan:
Pasang modul express dan mysql dengan menjalankan perintah: bash Copy code npm install express mysql

Buat Server Express:
Buat berkas app.js atau index.js dan konfigurasikan server Express. javascript Copy code const express = require('express'); const app = express(); const port = 3000;

app.get('/', (req, res) => { res.send('Hello World!'); });

app.listen(port, () => { console.log(Server berjalan di http://localhost:${port}); });

Koneksi ke MySQL:
Tambahkan koneksi ke MySQL di berkas app.js. javascript Copy code const mysql = require('mysql');

const connection = mysql.createConnection({ host: 'localhost', user: 'root', password: 'password', database: 'nama_database', });

connection.connect((err) => { if (err) { console.error('Koneksi ke MySQL gagal: ' + err.stack); return; } console.log('Terhubung ke MySQL dengan ID ' + connection.threadId); });

Buat Tabel Biodata Siswa di MySQL:
Gunakan MySQL untuk membuat tabel siswa atau sesuai dengan kebutuhan Anda.

Tambahkan Endpoint untuk Mengambil Biodata Siswa:
Modifikasi berkas app.js untuk menambahkan endpoint yang mengambil biodata siswa dari database MySQL. javascript Copy code app.get('/biodata-siswa', (req, res) => { const query = 'SELECT * FROM siswa';

connection.query(query, (error, results, fields) => { if (error) throw error; res.json(results); }); }); 8. Jalankan Server:

Jalankan server dengan perintah node app.js atau sesuai dengan nama berkas yang Anda gunakan. Uji Coba:

Buka browser dan akses http://localhost:3000/biodata-siswa untuk melihat data siswa yang diambil dari MySQL. Pastikan Anda mengganti informasi koneksi MySQL dengan yang sesuai dengan konfigurasi server MySQL Anda.