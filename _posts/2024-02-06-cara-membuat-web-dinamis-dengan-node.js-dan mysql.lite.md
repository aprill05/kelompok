Jika Anda ingin membuat web dinamis dengan Node.js dan SQLite (bukan MySQL Lite, karena MySQL Lite tidak ada),
berikut adalah langkah-langkah umum yang dapat Anda ikuti:

1. Persiapkan Lingkungan:

Pastikan Anda telah menginstal Node.js di sistem Anda. Anda dapat mengunduhnya dari situs resmi Node.js.
Jika belum ada, instal SQLite, sebuah database ringan dan serverless.

2. Inisialisasi Proyek Node.js:

Buat direktori proyek baru dan masuk ke dalamnya melalui terminal.
Jalankan perintah npm init untuk membuat berkas package.json dan ikuti petunjuk untuk mengisi informasi proyek.

3. Pasang Modul yang Dibutuhkan:

Pasang modul express dan sqlite3 dengan menjalankan perintah:
bash
Copy code
npm install express sqlite3

4. Buat Server Express:

Buat berkas app.js atau index.js dan konfigurasikan server Express.
javascript
Copy code
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(port, () => {
  console.log(`Server berjalan di http://localhost:${port}`);
});

5. Koneksi ke SQLite:

Tambahkan koneksi ke SQLite di berkas app.js.
javascript
Copy code
const express = require('express');
const sqlite3 = require('sqlite3');
const app = express();
const port = 3000;

const db = new sqlite3.Database(':memory:'); // Gunakan ':memory:' untuk database in-memory

db.serialize(() => {
  // Buat tabel siswa
  db.run('CREATE TABLE siswa (id INT, nama TEXT, kelas TEXT)');

  // Isi data contoh
  const stmt = db.prepare('INSERT INTO siswa VALUES (?, ?, ?)');
  stmt.run(1, 'John Doe', 'XI IPA');
  stmt.run(2, 'Jane Doe', 'XII IPS');
  stmt.finalize();
});

app.get('/biodata-siswa', (req, res) => {
  const query = 'SELECT * FROM siswa';

  db.all(query, (err, rows) => {
    if (err) throw err;
    res.json(rows);
  });
});

app.listen(port, () => {
  console.log(`Server berjalan di http://localhost:${port}`);
});

6. Jalankan Server:

Jalankan server dengan perintah node app.js atau sesuai dengan nama berkas yang Anda gunakan.
Uji Coba:

Buka browser dan akses http://localhost:3000/biodata-siswa untuk melihat data siswa yang diambil dari SQLite.
Pastikan Anda menyesuaikan skema tabel, query, dan logika aplikasi sesuai dengan kebutuhan proyek Anda.
Juga, ingatlah untuk menambahkan lapisan keamanan, validasi input, dan manajemen kesalahan untuk proyek yang lebih besar dan lebih kompleks.




