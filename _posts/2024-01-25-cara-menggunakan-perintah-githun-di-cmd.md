---
layout: post
title:  "cara menggunakan perintah github di cmd"
date:   2024-01-25 13:28:55 +0800
categories: jekyll update
---




Untuk menggunakan perintah Git di Command Prompt (CMD) atau Command Prompt di Windows, berikut adalah langkah-langkah dasarnya:

Buka Command Prompt:

Tekan Win + R, ketik cmd, dan tekan Enter. Navigasi ke Direktori Proyek:

Gunakan perintah cd untuk berpindah ke direktori proyek Anda. bash

Copy code cd path/to/your/project Inisialisasi Repositori Git (jika belum):

Jika proyek Anda belum merupakan repositori Git, inisialisasikan dengan perintah: bash

Copy code git init Tambahkan File ke Indeks:

Tambahkan file ke indeks untuk persiapan commit: bash

Copy code git add nama_file atau untuk menambahkan semua file: bash

Copy code git add . Commit Perubahan:

Buat commit untuk menyimpan perubahan yang telah Anda tambahkan ke indeks: bash

Copy code git commit -m "Pesan commit Anda" Lihat Status Perubahan:

Periksa status perubahan yang belum dicommit: bash

Copy code git status Lihat Log Commit:

Lihat log commit untuk melihat sejarah perubahan: bash

Copy code git log Remote Repositori (Opsional):

Jika proyek Anda ada di repositori eksternal (seperti di GitHub), tambahkan remote repository: bash

Copy code git remote add origin URL_repositori Push Perubahan ke Repositori Eksternal (Opsional):

Kirim perubahan ke repositori eksternal (misalnya, GitHub): bash

Copy code git push -u origin branch_name Gantilah "branch_name" dengan nama branch yang sesuai. Pull Perubahan dari Repositori Eksternal (Opsional):

Tarik perubahan dari repositori eksternal: bash

Copy code git pull origin branch_name Gantilah "branch_name" dengan nama branch yang sesuai. Itulah beberapa perintah dasar Git yang dapat Anda gunakan melalui Command Prompt. Pastikan Git telah terinstal dan terkonfigurasi dengan benar di komputer Anda sebelumnya. Jika Anda belum menginstal Git, Anda dapat mengunduhnya dari Git Official Website.