---
layout: post
title:  "cara menambahkan gambar di jekyll"
date:   2024-01-30 13:28:55 +0800
categories: jekyll update
---
Untuk menambahkan gambar di situs web yang menggunakan Jekyll, Anda perlu mengikuti beberapa langkah sederhana. Berikut adalah panduan umum:

Tempatkan Gambar di Folder assets atau images:

Buat folder baru di direktori root proyek Jekyll Anda, misalnya, assets atau images. Tempatkan gambar-gambar yang ingin Anda tambahkan ke situs web di dalam folder tersebut. Edit File Markdown atau HTML:

Buka file Markdown atau HTML tempat Anda ingin menambahkan gambar. Gunakan sintaks Markdown untuk menambahkan gambar ke file Markdown atau gunakan tag  untuk file HTML. Sintaks Markdown:

Jika Anda menggunakan file Markdown (biasanya memiliki ekstensi .md), gunakan sintaks berikut untuk menambahkan gambar:

markdown Copy code Alt teks Gantilah /path/to/image.jpg dengan jalur relatif dari file Markdown ke gambar. Misalnya, jika gambar berada di dalam folder assets:

markdown Copy code Alt teks Tag HTML:

Jika Anda menggunakan file HTML, Anda dapat menggunakan tag  seperti berikut:

html Copy code Alt teks Gantilah /path/to/image.jpg dengan jalur relatif dari file HTML ke gambar.

Jalankan Jekyll:

Simpan perubahan Anda dan jalankan server Jekyll untuk melihat perubahan secara lokal. Gunakan perintah:

bash Copy code bundle exec jekyll serve Buka browser dan kunjungi http://localhost:4000 atau sesuai dengan port yang ditetapkan oleh Jekyll.

Periksa Situs Web Anda:

Buka halaman yang telah Anda edit dan pastikan gambar ditampilkan dengan benar. Pastikan untuk menggantikan Alt teks dengan deskripsi singkat gambar yang Anda tambahkan. Ini membantu dalam aksesibilitas dan SEO. Juga, pastikan gambar-gambar tersebut ada dan dapat diakses di jalur yang Anda tentukan.