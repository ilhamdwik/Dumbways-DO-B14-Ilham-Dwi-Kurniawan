# Tugas Stage 2 Week 1

## appserver - 1 CPU, 2GB RAM & 20GB Storage

![01](assets/nomer1/3.png)

![02](assets/nomer1/5.png)

![03](assets/nomer1/6.png)


## gateway - 1 CPU, 1GB RAM & 20GB Storage

![01](assets/nomer1/4.png)

![02](assets/nomer1/5.png)

![03](assets/nomer1/7.png)


## 1. Koneksi SSH antara client/device kalian ke IDCH tanpa password

* #### Pertama lakukan command sebagai berikut untuk men-generate kunci beserta gembok diubuntu kita. Kunci dan gembok inilah yang akan menghubungkan ubuntu kita dengan server yang akan kita remote (ssh).
``` 
ssh-keygen
```
![01](assets/nomer1/1.png)

* #### Lalu cek apakah berhasil sudah berhasil dibuat didalam file .ssh .
``` 
cd .ssh

cat kunci_ilhaskam_idch.pub
```
![02](assets/nomer1/2.png)

* #### Gunakan perintah scp (secure copy) untuk mengcopy file dari ubuntu kita ke server tujuan kita. Dengan penambahan command -r (recursive) berarti kita mengcopy banyak file.
``` 
scp -r (nama_file_di_ubuntu_kita) username_server_tujuan@ip_server_tujuan:(direktori_tujuan)
```
![03](assets/nomer1/8.png)

* #### Lalu copy paste semua yang berada di kunci_ilhaskam_idch.pub ke dalam direktori .ssh/authorized_keys yang berada di server remote.
``` 
cat kunci_ilhaskam_idch.pub

cd .ssh

nano authorized_keys
```
![04](assets/nomer1/9.png)

![05](assets/nomer1/10.png)

* #### Lalu coba untuk remote server menggunakan command berikut. -i artinya inventory yang berarti kita mengakses inventori di dalam ubuntu kita.
``` 
ssh -i (file_kunci_disimpan) (username_tujuan)@(ip_tujuan)
```
![06](assets/nomer1/11.png)

![07](assets/nomer1/12.png)


## 2. Deploy Aplikasi Dumbflix menggunakan database MySQL

### - Database terhubung dengan Backend

* #### Pertama untuk menjalankan aplikasi backend setup terlebih dahulu databasenya. Install database mysql.
``` 
sudo apt install mysql-server
```
![01](assets/nomer2/setup_database_mysql/1.png)

* #### Cek versi database mysql.
``` 
mysql --version
```
![02](assets/nomer2/setup_database_mysql/2.png)

* #### Masuk ke user root database mysql.
``` 
sudo mysql -u (nama_user)
```
![03](assets/nomer2/setup_database_mysql/3.png)

* #### Berikan password untuk user root.
``` 
ALTER USER 'nama_user'@'localhost' IDENTIFIED WITH mysql_native_password by 'password_baru';

atau bisa juga menggunakan command dibawah,keduanya sama saja.

ALTER USER 'nama_user'@'localhost' IDENTIFIED BY 'password_baru';
```
![04](assets/nomer2/setup_database_mysql/4.png)

![05](assets/nomer2/setup_database_mysql/6.png)

* #### Lalu amankan database mysql kalian menggunakan mysql_secure_installation. Lalu ikuti step by step berikut ini.
``` 
sudo mysql_secure_installation
```
![06](assets/nomer2/setup_database_mysql/7.png)

![07](assets/nomer2/setup_database_mysql/8.png)

![08](assets/nomer2/setup_database_mysql/9.png)

![09](assets/nomer2/setup_database_mysql/10.png)

![10](assets/nomer2/setup_database_mysql/11.png)

* #### Masuk menggunakan root dengan -p yang atinya menggunakan password.
``` 
sudo mysql -u root -p
```
![11](assets/nomer2/setup_database_mysql/12.png)

* #### Create user di dalam database mysql.
``` 
CREATE USER 'nama_user'@'%' IDENTIFIED BY 'password_anda';
```
![12](assets/nomer2/setup_database_mysql/13.png)

![13](assets/nomer2/setup_database_mysql/14.png)

* #### Berikan akses user ilham untuk mengakses seluruh database yang ada didalam mysql server.
``` 
GRANT ALL PRIVILEGES ON *.* TO 'nama_user'@'%';
```
![14](assets/nomer2/setup_database_mysql/15.png)

* #### Clone aplikasi backend.
``` 
git clone https://github.com/dumbwaysdev/dumbflix-backend.git
```
![15](assets/nomer2/install_aplikasi_backend/1.png)

![16](assets/nomer2/install_aplikasi_backend/2.png)

* #### Configurasi file config/config.json ubah sesuai dengan user dan password yang sudah kita buat tadi.
![17](assets/nomer2/install_aplikasi_backend/3.png)

![18](assets/nomer2/install_aplikasi_backend/4.png)

* #### Install sequelize cli dan copy .env.example ke .env.
```
npm install -g sequelize cli

cp .env-copy .env
```
![19](assets/nomer2/install_aplikasi_backend/5.png)

* #### Dikarenakan saya sudah copy file .env nya maka hasilnya seperti ini.
![20](assets/nomer2/install_aplikasi_backend/6.png)

* #### Dengan sequelize kita bisa langsung menggunakan perintah db create untuk membuat database. Kita juga bisa mengenerate table dari aplikasi backend dumbflix dengan perintah db:migrate. Dikarenakan dumbflix-backend menggunakan ORM sequelize, maka proses create database dan migrate bisa lebih cepat.
```
npx sequelize db:create

npx sequelize db:migrate
```

* #### Cek apakah database sudah terbuat.
```
show databases;
```
![21](assets/nomer2/install_aplikasi_backend/7.png)

* #### Memilih database dumbflix.
```
use dumbflix;
```
![22](assets/nomer2/install_aplikasi_backend/8.png)

* #### Menampilkan table di dalam database dumbflix.
```
show tables;
```
![23](assets/nomer2/install_aplikasi_backend/9.png)

* #### Menampilkan data dari table Users yang ada didalam database dumbflix.
```
SELECT * FROM Users;
```
![24](assets/nomer2/install_aplikasi_backend/10.png)


### - Frontend dan Backend dapat diakses menggunakan domain nama.studentdumbways.my.id


## 3. Pastikan domain kalian bisa diakses menggunakan HTTPS

## Challenge
### - HTTPS menggunakan wildcard
### - Koneksi Reverse Proxy tidak menggunakan public IP

### Repository
### https://github.com/dumbwaysdev/dumbflix-frontend
### https://github.com/dumbwaysdev/dumbflix-backend