
Jika Anda ingin menginstal daloradius di Ubuntu 21.10 atau versi sebelumnya, berikut adalah langkah-langkah umumnya:

1. Persiapkan Ubuntu: Pastikan Anda memiliki akses root atau akses sudo di sistem Ubuntu Anda.

2. Perbarui Repositori: Jalankan perintah berikut untuk memperbarui indeks paket dan menginstal paket-paket yang diperlukan:

bash
Copy code
sudo apt update
sudo apt upgrade

3. Instalasi Apache, MySQL, PHP: Daloradius membutuhkan server web (Apache), server basis data (MySQL), dan interpreter bahasa pemrograman (PHP). Instalasi paket-paket ini dengan perintah:

bash
Copy code
sudo apt install apache2 mysql-server php php-mysql php-gd php-common php-curl php-mail php-mail-mime

4. Konfigurasi MySQL: Secara opsional, Anda dapat mengamankan instalasi MySQL dengan menjalankan:

bash
Copy code
sudo mysql_secure_installation
Ikuti petunjuk pada layar untuk mengatur kata sandi root MySQL dan menghapus pengaturan yang tidak aman.

5. Unduh dan Instal Daloradius: Unduh paket Daloradius dari situs web resminya atau dari repositori GitHub. Ekstrak paket tersebut dan pindahkan ke direktori web root:

bash
Copy code
sudo mkdir /var/www/html/daloradius
sudo cp -r daloradius_folder/* /var/www/html/daloradius

6. Konfigurasi Daloradius: Salin file konfigurasi contoh dan ubah sesuai kebutuhan Anda:

bash
Copy code
sudo cp /var/www/html/daloradius/library/daloradius.conf.php.example /var/www/html/daloradius/library/daloradius.conf.php

7.Impor Skema Basis Data: Masuk ke MySQL dan buat basis data untuk Daloradius. Kemudian, impor skema basis data yang disertakan:

bash
Copy code
sudo mysql -u root -p

Setelah masuk, jalankan perintah-perintah berikut:

sql
Copy code
CREATE DATABASE daloradius;
GRANT ALL ON daloradius.* TO 'radius'@'localhost' IDENTIFIED BY 'radpass';
FLUSH PRIVILEGES;
EXIT;
sudo mysql -u root -p daloradius < /var/www/html/daloradius/contrib/db/fr2-mysql-daloradius-and-freeradius.sql

8. Konfigurasi Freeradius: Ubah konfigurasi Freeradius agar menggunakan Daloradius sebagai antarmuka web. Edit file /etc/freeradius/3.0/sites-available/default dan sesuaikan seperti ini:

bash
Copy code
$INCLUDE sql.conf
$INCLUDE daloradius.conf

9. Mulai Ulang Freeradius dan Apache: Setelah mengonfigurasi Freeradius, mulai ulang Freeradius dan Apache untuk menerapkan perubahan:

bash
Copy code
sudo systemctl restart freeradius
sudo systemctl restart apache2

10. Akses Daloradius: Buka browser web dan akses Daloradius di alamat http://localhost/daloradius. 
   Masuk menggunakan username dan password default (biasanya administrator dan radius).



code install freeradius

1. sudo apt update
   sudo apt upgrade

2. sudo apt -y install apache2

3. sudo systemctl enable --now apache2

4. sudo ufw allow WWW

5. sudo apt -y install php libapache2-mod-php php-{gd,common,mail,mail-mime,mysql,pear,db,mbstring,xml,curl}

6. php -v

7. sudo apt -y install mariadb-server
   sudo apt -y install mysql-server

8. sudo apt -y install mariadb-server

9. sudo mysql_secure_installation

10. Enter current password for root (enter for none):



code freeradius


login ubuntu,password

1. sudo apt update
2. sudo install freeradius
3. sudo service freeradius start
4. sudo service freeradius status
5. 


