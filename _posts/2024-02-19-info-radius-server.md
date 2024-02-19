Untuk menginstal server RADIUS pada sistem operasi Linux, salah satu pilihan yang umum adalah menggunakan paket perangkat lunak bernama FreeRADIUS.
FreeRADIUS adalah server RADIUS open-source yang banyak digunakan dalam berbagai skenario jaringan.
Di bawah ini adalah langkah-langkah umum untuk menginstal FreeRADIUS di distribusi Linux seperti Ubuntu atau Debian:

1. Buka Terminal:

   Buka terminal di sistem Anda. Anda dapat menemukan terminal di menu aplikasi atau menggunakan pintasan keyboard seperti Ctrl + Alt + T.

2. Update Paket Repository:
 
    Pastikan paket repository sistem Anda diperbarui dengan menjalankan perintah:

sql
Copy code
sudo apt update
3. Instal FreeRADIUS:

Setelah repository diperbarui, instal FreeRADIUS dengan menjalankan perintah:

Copy code
sudo apt install freeradius

4. Verifikasi Instalasi:

Setelah instalasi selesai, Anda dapat memverifikasi apakah FreeRADIUS berhasil diinstal dengan menjalankan perintah:

Copy code
freeradius -v
Perintah tersebut akan menampilkan versi FreeRADIUS yang terinstal, menunjukkan bahwa instalasi telah berhasil.

5. Konfigurasi FreeRADIUS:

   Konfigurasi FreeRADIUS terletak di direktori /etc/freeradius. Anda dapat menyesuaikan konfigurasi sesuai dengan kebutuhan Anda, termasuk mengatur parameter otentikasi, otorisasi, dan akuntansi.

6. Mulai Layanan FreeRADIUS:

   Jalankan perintah berikut untuk memulai layanan FreeRADIUS:

sql
Copy code
sudo service freeradius start
Anda juga dapat menggunakan perintah restart atau stop untuk memulai ulang atau menghentikan layanan FreeRADIUS.

7. Verifikasi Layanan:

   Anda dapat memeriksa apakah FreeRADIUS berjalan dengan baik dengan memeriksa status layanan:

lua
Copy code
sudo service freeradius status

Jika layanan berjalan dengan baik, Anda akan melihat pesan yang menunjukkan bahwa layanan sedang berjalan.

Setelah mengikuti langkah-langkah di atas, Anda telah berhasil menginstal dan menjalankan server RADIUS menggunakan FreeRADIUS di sistem Linux Anda. 
Selanjutnya, Anda dapat melakukan konfigurasi lebih lanjut sesuai dengan kebutuhan jaringan Anda, seperti menambahkan pengguna, mengatur klien RADIUS, dan lain-lain.




**info lainnya:**

Untuk menginstal dan mengkonfigurasi perangkat MikroTik sebagai server RADIUS di sistem Linux, Anda perlu menggunakan RouterOS MikroTik yang memiliki fitur RADIUS Server. Saat ini, RouterOS MikroTik tidak didukung pada sistem operasi Linux standar. Namun, Anda bisa menggunakan MikroTik sebagai server RADIUS di jaringan Anda.

Berikut adalah langkah-langkah umum untuk mengkonfigurasi MikroTik sebagai server RADIUS di jaringan Anda:

1. Persiapkan Perangkat MikroTik:

Pastikan Anda memiliki perangkat MikroTik yang mendukung fitur RADIUS Server. Ini biasanya termasuk router seri RouterBOARD atau perangkat MikroTik lainnya yang menjalankan RouterOS.

2. Masuk ke Perangkat MikroTik:

Gunakan antarmuka pengelolaan MikroTik, seperti Winbox atau antarmuka web (dengan mengakses alamat IP perangkat), untuk masuk ke perangkat MikroTik menggunakan kredensial admin.

3. Aktifkan Layanan RADIUS:

Di antarmuka MikroTik, Anda perlu mengaktifkan layanan RADIUS. Anda bisa melakukannya melalui Winbox atau CLI (Command Line Interface). Misalnya, di CLI, Anda bisa menggunakan perintah berikut:

bash
Copy code
/radius add service=login,address=192.168.1.100 secret=myradiussecret
Di sini, address adalah alamat IP dari server RADIUS Anda dan secret adalah kata sandi yang digunakan untuk mengamankan koneksi antara perangkat MikroTik dan server RADIUS.

4. Konfigurasi Pengguna RADIUS:

   Setelah RADIUS diaktifkan, Anda perlu menambahkan pengguna RADIUS. Ini bisa dilakukan langsung di antarmuka MikroTik. Masuk ke menu "PPP" atau "User" dan tambahkan pengguna baru dengan jenis otentikasi RADIUS.

5. Uji Koneksi dan Otentikasi:

  Setelah konfigurasi selesai, uji koneksi dan otentikasi pengguna menggunakan kredensial yang telah Anda atur.

6. Monitor dan Atur Logging:

  Penting untuk memantau dan melacak aktivitas RADIUS Anda. Anda dapat melakukannya melalui antarmuka MikroTik, baik itu melalui Winbox atau melalui CLI.

Itulah langkah-langkah umum untuk mengkonfigurasi perangkat MikroTik sebagai server RADIUS.
Pastikan untuk mengacu pada dokumentasi resmi MikroTik dan memperhatikan kebutuhan jaringan Anda untuk konfigurasi yang tepat.
