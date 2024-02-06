Untuk membuat web dinamis dengan Node.js dan SQLite yang memiliki operasi CRUD (Create, Read, Update, Delete) pada biodata, Anda dapat mengikuti langkah-langkah berikut:

##Langkah 1: Instalasi Node.js dan npm

Pastikan Node.js dan npm (Node Package Manager) terinstal di sistem Anda. Anda dapat mengunduhnya dari situs resmi Node.js: https://nodejs.org/

##Langkah 2: Inisialisasi Proyek Node.js

Buat direktori baru untuk proyek Anda, lalu buka terminal dan navigasikan ke direktori tersebut. Jalankan perintah berikut untuk menginisialisasi proyek Node.js:

bash
Copy code
npm init -y

##Langkah 3: Instalasi Paket-paket yang Diperlukan

Instal paket-paket Node.js yang diperlukan untuk membuat web server dan bekerja dengan SQLite:

bash
Copy code
npm install express sqlite3 body-parser
express: Untuk membuat web server.
sqlite3: Untuk berinteraksi dengan SQLite.
body-parser: Untuk mengurai data yang dikirimkan dalam permintaan HTTP.

##Langkah 4: Membuat Struktur Proyek

Buat struktur dasar proyek dengan membuat direktori public untuk file statis (CSS, JavaScript), views untuk tampilan, dan routes untuk mengelola rute aplikasi.

##Langkah 5: Membuat Database SQLite

Buat file database.db sebagai basis data SQLite Anda. Anda dapat menggunakan alat seperti DB Browser for SQLite untuk membuat tabel dan mengelola data.

##Langkah 6: Menulis Kode Aplikasi

Buat file app.js di direktori proyek Anda dan tambahkan kode berikut:

javascript
Copy code
const express = require('express');
const bodyParser = require('body-parser');
const sqlite3 = require('sqlite3').verbose();

const app = express();
const port = 3000;

app.use(bodyParser.urlencoded({ extended: true }));
app.use(express.static('public'));

const db = new sqlite3.Database('database.db');

app.get('/', (req, res) => {
  db.all('SELECT * FROM biodata', (err, rows) => {
    if (err) {
      console.error(err.message);
      res.status(500).send('Internal Server Error');
    } else {
      res.render('index.ejs', { biodata: rows });
    }
  });
});

app.get('/add', (req, res) => {
  res.render('add.ejs');
});

app.post('/add', (req, res) => {
  const { nama, usia, alamat } = req.body;
  db.run('INSERT INTO biodata (nama, usia, alamat) VALUES (?, ?, ?)', [nama, usia, alamat], (err) => {
    if (err) {
      console.error(err.message);
      res.status(500).send('Internal Server Error');
    } else {
      res.redirect('/');
    }
  });
});

app.get('/edit/:id', (req, res) => {
  const id = req.params.id;
  db.get('SELECT * FROM biodata WHERE id = ?', [id], (err, row) => {
    if (err) {
      console.error(err.message);
      res.status(500).send('Internal Server Error');
    } else {
      res.render('edit.ejs', { biodata: row });
    }
  });
});

app.post('/edit/:id', (req, res) => {
  const { nama, usia, alamat } = req.body;
  const id = req.params.id;
  db.run('UPDATE biodata SET nama = ?, usia = ?, alamat = ? WHERE id = ?', [nama, usia, alamat, id], (err) => {
    if (err) {
      console.error(err.message);
      res.status(500).send('Internal Server Error');
    } else {
      res.redirect('/');
    }
  });
});

app.get('/delete/:id', (req, res) => {
  const id = req.params.id;
  db.run('DELETE FROM biodata WHERE id = ?', [id], (err) => {
    if (err) {
      console.error(err.message);
      res.status(500).send('Internal Server Error');
    } else {
      res.redirect('/');
    }
  });
});

app.listen(port, () => {
  console.log(`Server is running at http://localhost:${port}`);
});

##Langkah 7: Membuat Tampilan (EJS)

Buat file tampilan index.ejs, add.ejs, dan edit.ejs di direktori views. Contoh index.ejs:

html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CRUD Biodata</title>
</head>
<body>
  <h1>List Biodata</h1>
  <ul>
    <% biodata.forEach((data) => { %>
      <li><%= data.nama %> - <%= data.usia %> tahun - <%= data.alamat %> (<a href="/edit/<%= data.id %>">Edit</a> | <a href="/delete/<%= data.id %>">Delete</a>)</li>
    <% }); %>
  </ul>
  <a href="/add">Tambah Biodata</a>
</body>
</html>

##Langkah 8: Menjalankan Aplikasi

Jalankan aplikasi dengan perintah:

bash
Copy code
node app.js
Buka browser dan akses http://localhost:3000 untuk melihat aplikasi CRUD Biodata dengan Node.js dan SQLite Anda.

Pastikan untuk menyusun file tampilan add.ejs dan edit.ejs dengan sesuai agar formulir tambah dan edit berfungsi dengan baik.






