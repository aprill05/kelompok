
---
layout: post
title:  "Perintah Git"
date:   2024-01-23 13:28:55 +0800
categories: jekyll update
---





Untuk membuat situs statis di GitHub menggunakan framework Jekyll, Anda dapat mengikuti langkah-langkah berikut:

1. Persiapkan Repositori GitHub:

 * Buat repositori baru di GitHub.
 * Pastikan nama repositorinya mengikuti format:
[username].github.io (ganti [username] dengan nama pengguna GitHub Anda).

2. Aktifkan GitHub Pages:

 * Buka halaman repositori di GitHub.
 * Pilih tab "Settings".
 * Gulir ke bawah hingga Anda menemukan bagian "GitHub Pages".
 * Pada opsi "Source", pilih branch yang berisi kode Jekyll (biasanya "main" atau "master").
 * Simpan perubahan.
 
3. Siapkan Proyek Jekyll Lokal:

 * Pastikan Anda telah menginstal Ruby dan bundler di komputer Anda.
 * Buka terminal dan pindah ke direktori tempat Anda ingin menyimpan proyek Jekyll.
 * Jalankan perintah berikut untuk membuat proyek Jekyll baru:

bash
Copy code
jekyll new nama_proyek

Gantilah nama_proyek sesuai keinginan Anda.

4. Konfigurasi:

 * Pindah ke direktori proyek Jekyll yang baru dibuat:

bash
Copy code
cd nama_proyek

 * Buka file _config.yml untuk konfigurasi dan sesuaikan pengaturannya sesuai kebutuhan Anda.

5. Uji Coba Situs Lokal:

 * Jalankan server Jekyll lokal untuk melihat situs Anda:

bash
Copy code
bundle exec jekyll serve

 * Buka browser dan kunjungi http://localhost:4000 untuk melihat situs lokal Anda.

6. Kustomisasi Konten:

 * Sesuaikan konten, tata letak, dan gaya sesuai kebutuhan Anda.
 * Gunakan Markdown atau HTML untuk menulis konten.

7. Push ke GitHub:

 * Setelah Anda puas dengan perubahan lokal, lakukan commit dan push ke repositori GitHub Anda:

bash
Copy code
git add .
git commit -m "Menambahkan situs Jekyll"
git push origin main

8.Lihat Situs Online:

 * Setelah melakukan push, situs Anda harus dapat diakses melalui [username].github.io.

9. Perbarui Konten:

 * Setiap kali Anda ingin memperbarui situs, lakukan langkah 7 dan situs GitHub Pages akan diperbarui secara otomatis.

Ini adalah langkah-langkah dasar untuk membuat situs statis di GitHub menggunakan Jekyll. 
