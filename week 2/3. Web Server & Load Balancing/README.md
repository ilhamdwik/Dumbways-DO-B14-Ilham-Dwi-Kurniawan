# Task : Web Server & Load Balancing

## 1. Definisi Web Server

* #### Web server adalah sebuah software (perangkat lunak) yang memberikan layanan berupa data. Berfungsi untuk menerima permintaan HTTP atau HTTPS dari klien atau kita kenal dengan web browser (Chrome, Firefox). Selanjutnya ia akan mengirimkan respon atas permintaan tersebut kepada client dalam bentuk halaman web.


## 2. Jalankan 2 VM
  ### - VM 1 = server
  ### - VM 2 = nginx



## 3. VM1 : jalankan aplikasi dumbflix-frontend - gunakan PM2

* #### Pertama jalankan aplikasi wayshub pada sisi server menggunakan pm2. Jika pada pm2 list status = online, maka aplikasi sudah berjalan di pm2.
``` 
pm2 start npm --name "wayshub-frontend" -- start
```
![01](assets/1.png)

* #### Coba akses aplikasi wayshub menggunakan ip dari sisi server. Jika berhasil maka aplikasi wayshub akan tampil.
![02](assets/2.png)


## 4. VM2 :

### - jalankan nginx 

* #### Selanjutnya install web server nginx pada sisi nginx.
![03](assets/3.png)


### - buat konfigurasi reverse proxy dengan domain (gunakan nama kalian) mengarah ke app di VM1

* #### Masuk ke direktori /etc/nginx. Pada direktori ini berisi file-file konfigurasi dari web server nginx.
![04](assets/4.png)

* #### Buat direktori untuk menyimpan file konfigurasi untuk membuat reverse proxy di dalam direktori /etc/nginx.
``` 
sudo mkdir dumbways
```
![05](assets/5.png)

* #### Buat file konfigurasi untuk membuat reverse proxy di dalam direktori /etc/nginx/dumbways.
``` 
sudo nano my.domain.conf
```
![06](assets/6.png)

* #### Lalu konfigurasi untuk membuat reverse proxy pada aplikasi wayshub. Tambahkan konfigurasi berikut di dalam file my.domain.conf
``` 
server { 
    server_name domain.com; 
    
    location / { 
             proxy_pass http://ip_server:3000;
    }
}
```
![07](assets/7.png)

* #### Selanjutnya tambahkan ip dari nginx beserta domain yang sudah dibuat sebelumnya ke dalam file /etc/hosts di ubuntu. 
``` 
sudo nano /etc/hosts

lalu tambahkan

(ip_dari_nginx) (domain) 
```
![08](assets/8.png)

* #### Lalu coba tes domain ilhamdwi.xyz.
``` 
curl ilhamdwi.xyz
```
![09](assets/9.png)

* #### Lalu akses di web browser.
``` 
curl ilhamdwi.xyz
```
![10](assets/10.png)

* #### Coba matikan aplikasi wayshub di pm2 pada sisi server.
``` 
pm2 stop (id)
```
![11](assets/11.png)

* #### Lalu coba akses kembali pada web browser. Maka akan muncul Gateway time out dikarenakan aplikasi wayshub di pm2 di stop.
![12](assets/12.png)


### - buat konfigurasi load balance antara VM1 dan VM2

* #### Untuk membuat load balance, edit file my.domain.conf.
``` 
upstream domain { 
    server (ip_server):3000;
    server (ip_nginx):3000;
}
server { 
    server_name ilhamdwi.xyz; 
  
    location / { 
             proxy_pass http://domain;
    }
}
```
![13](assets/13.png)

* #### Lalu coba akses aplikasi di web browser apakah berjalan lancar atau tidak.
![14](assets/14.png)

* #### Coba matikan aplikasi wayshub di salah satu server.
![15](assets/15.png)

* #### Coba matikan aplikasi wayshub di semua server.
![16](assets/16.png)

* #### Coba matikan aplikasi wayshub di salah satu server.
![17](assets/17.png)

* #### Coba jalankan aplikasi wayshub di semua server.
![18](assets/18.png)


## 5. Domain bisa diakses melalui web browser kalian

* #### Coba jalankan aplikasi wayshub di semua server.
![19](assets/19.png)


### Challenge
### Load Balancer berjalan dengan baik

![15](assets/15.png)

![16](assets/16.png)

![17](assets/17.png)

![18](assets/18.png)