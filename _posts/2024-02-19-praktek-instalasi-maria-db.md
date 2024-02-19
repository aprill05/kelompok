MATERI PARAKTEK INSTALASI MARIADB

1. Pengenalan MariaDB
   
•	MariaDB adalah sistem manajemen basis data (SMBD) open-source yang kompatibel dengan MySQL.
•	MariaDB dikembangkan oleh komunitas pengembang yang dipimpin oleh Michael "Monty" Widenius, salah satu pendiri MySQL.

2. Instalasi MariaDB

•	Anda dapat mengunduh dan menginstal MariaDB dari situs web resminya atau menggunakan manajer paket pada sistem operasi Anda.
•	Contoh instalasi di sistem operasi Ubuntu menggunakan terminal:
•	sudo apt update
•	sudo apt install mariadb-serversudo apt update sudo apt install mariadb-server 

3. Menghubungkan ke Server MariaDB

•	Setelah instalasi selesai, Anda dapat terhubung ke server MariaDB menggunakan perintah berikut:
mysql -u username -pmysql -u username -p 
•	Anda akan diminta untuk memasukkan kata sandi yang sesuai.

4. Membuat Basis Data
   
•	Basis data adalah kumpulan tabel yang terorganisir untuk menyimpan data.
•	Contoh membuat basis data baru dengan nama "contoh":
CREATE DATABASE contoh;

5. Membuat Tabel

•	Tabel adalah struktur dasar untuk menyimpan data dalam basis data.
Berikut adalah contoh pembuatan tabel biodata siswa di MariaDB:
CREATE TABLE biodata_siswa (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nama VARCHAR(50),
    jenis_kelamin ENUM('Laki-laki', 'Perempuan'),
    tanggal_lahir DATE,
    alamat TEXT
);

Penjelasan:

1.	id: Kolom ini digunakan sebagai primary key (kunci utama) tabel. Nilainya akan secara otomatis bertambah setiap kali sebuah baris baru ditambahkan ke tabel (AUTO_INCREMENT).

2.	nama: Kolom ini akan menyimpan nama siswa dengan tipe data VARCHAR(50), yang berarti nama dapat memiliki maksimal 50 karakter.

3.	jenis_kelamin: Kolom ini akan menyimpan informasi jenis kelamin siswa. Tipe datanya adalah ENUM yang membatasi nilai yang dapat dimasukkan hanya pada nilai yang telah ditentukan ('Laki-laki' atau 'Perempuan').

4.	tanggal_lahir: Kolom ini akan menyimpan tanggal lahir siswa dengan tipe data DATE.

5.	alamat: Kolom ini akan menyimpan alamat siswa dengan tipe data TEXT, yang berarti dapat menyimpan teks dengan panjang yang lebih besar daripada VARCHAR.

6. Menyisipkan Data ke dalam Tabel

•	Setelah membuat tabel, Anda dapat menyisipkan data ke dalamnya menggunakan perintah INSERT INTO.
Berikut adalah contoh penyisipan data ke dalam tabel biodata_siswa yang baru saja dibuat:
INSERT INTO biodata_siswa (nama, jenis_kelamin, tanggal_lahir, alamat) 
VALUES 
    ('Ani', 'Perempuan', '2005-05-15', 'Jl. Merdeka No. 10, Jakarta'),
    ('Budi', 'Laki-laki', '2004-09-20', 'Jl. Cendrawasih No. 5, Surabaya'),
    ('Citra', 'Perempuan', '2006-02-10', 'Jl. Pahlawan No. 8, Bandung'),
    ('Dewi', 'Perempuan', '2005-11-30', 'Jl. Diponegoro No. 15, Yogyakarta'),
    ('Eko', 'Laki-laki', '2004-07-25', 'Jl. Gatot Subroto No. 12, Semarang');

Perintah di atas akan menyisipkan lima baris data ke dalam tabel biodata_siswa. Setiap baris menyertakan nama, jenis kelamin, tanggal lahir, dan alamat siswa.

Untuk melihat hasilnya, Anda dapat menggunakan perintah SELECT untuk mengambil data dari tabel biodata_siswa. Berikut adalah contoh perintah untuk melihat semua data dalam tabel:
SELECT * FROM biodata_siswa;

SELESAI.............................................................!
