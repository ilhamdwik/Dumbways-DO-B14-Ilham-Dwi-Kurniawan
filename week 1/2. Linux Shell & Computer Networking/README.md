# Task : Linux Shell & Computer Networking


### 1. Perbedaan antara IP private & public

* #### IP public adalah alamat IP yang digunakan dalam jaringan global Internet. Diberikan oleh penyedia layanan internet (ISP), dimana terdapat informasi sehingga dapat dilacak.

* #### IP private adalah alamat IP yang digunakan dalam jaringan local dan tidak bisa diakses dari jaringan internet secara langsung.


### 2. Perbedaan antara IP dinamis & statis

* #### IP Address Dinamis merupakan pemberian IP secara otomatis dalam sebuah jaringan baik itu bersifat IP publik atau IP private. IP ini akan berubah-ubah setiap waktu.

* #### IP Address Statis merupakan pemberian IP yang tidak akan berubah, harus di konfigurasi manual jika ingin menggunakan IP statis.


### 3. Deploy aplikasi web server apache menggunakan apt package

* #### Pertama install apache web server menggunakan command "sudo apt install apache2".
![01](assets/Screenshot(151).png)

* #### Untuk melihat file konfigurasi dari apache web server masuk ke direktori /etc/apache2/sites-available, Lalu buka menggunakan nano 000-default.conf.
![02](assets/Screenshot(152).png)

* #### Pada file 000-default.conf berisi konfigurasi dari apache web server.
![03](assets/Screenshot(153).png)

* #### Cek ip dari server di linux menggunakan command ifconfig.
![04](assets/Screenshot(154).png)

* #### Buka browser dan masukkan ip dari server.
![05](assets/Screenshot(155).png)
