# Stage 2 Day 4 | Docker		


## appserver - 2 CPU, 2GB RAM
* #### Buat VM di idcloudhost (nama Kelompok3-Appserver)
![01](assets/vm/vm_appserver.png)


## gateway - 1 CPU, 1GB RAM
* #### Buat VM di idcloudhost (nama Kelompok3-Gateway)
![02](assets/vm/vm_gateway.png)


## Storage 20GB
* #### Buat VM di idcloudhost
![03](assets/vm/vm_appserver.png)
![04](assets/vm/vm_gateway.png)


## 1. Instalasi Docker
* #### Untuk menginstall docker ikuti langkah-langkah berikut ini.
``` 
sudo apt-get remove docker docker-engine docker.io containerd runc

sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
![05](assets/Dokumentasi-Docker/install_docker_in_server/1.png)
![06](assets/Dokumentasi-Docker/install_docker_in_server/2.png)
![07](assets/Dokumentasi-Docker/install_docker_in_server/3.png)
![08](assets/Dokumentasi-Docker/install_docker_in_server/4.png)


## 2. Deploy Aplikasi - menggunakan database MySQL & berfungsi dengan baik
* #### Clone aplikasi dari github.
![09](assets/git_clone/git_clone.png)
![10](assets/git_clone/cek_file_wayshub.png)


### - Jalankan on top Docker, gunakan docker-compose
* #### Masuk ke direktori wayshub-frontend. Lalu buat Dockerfile di dalam direktori wayshub-frontend.
![11](assets/Dokumentasi-Docker/1.png)

* #### Masuk ke direktori wayshub-frontend. Lalu buat docker-compose.yml di dalam direktori wayshub-frontend.
![12](assets/Dokumentasi-Docker/4.png)

* #### Masuk ke direktori wayshub-backend. Lalu buat Dockerfile di dalam direktori wayshub-backend.
![13](assets/Dokumentasi-Docker/2.png)

* #### Masuk ke direktori wayshub-backend. Lalu buat docker-compose.yml di dalam direktori wayshub-backend.
![14](assets/Dokumentasi-Docker/5.png)

* #### Lalu buat docker-compose untuk database mysql, pada kasus ini saya membuat docke-compose.yml diluar direktori dari wayshub-frontend & wayshub-backend.
![15](assets/Dokumentasi-Docker/3.png)

* #### Untuk menjalankan aplikasi di dalam docker, masuk terlebih dahulu di dalam direktori masing-masing, masuk direktori wayshub-frontend, lalu ketikkan perintah berikut ini.
```
docker compose up -d
```

* #### Untuk menjalankan aplikasi di dalam docker, masuk terlebih dahulu di dalam direktori masing-masing, masuk direktori wayshub-backend, lalu ketikkan perintah berikut ini.
```
docker compose up -d
```

* #### Lalu cek apakah aplikasi sudah berjalan di atas docker.
```
docker ps -a
```
![16](assets/Dokumentasi-Docker/6.png)

```
docker images
```
![17](assets/Dokumentasi-Docker/7.png)

### - Push image ke hub Docker menggunakan akun masing-masing

![18](assets/docker_push_docker_hub/1.png)
![19](assets/docker_push_docker_hub/2.png)
![20](assets/docker_push_docker_hub/3.png)
![21](assets/docker_push_docker_hub/4.png)


## 3. Reverse Proxy & SSL Certificate untuk domain aplikasi

* #### Step-step untuk mengaktifkan DNS SSL menggunakan certbot wildcard. Untuk step lebih lengkapnya bisa dilihat di website certbot, karena disini kita lupa untuk mencapture proses secara lengkapnya.

![22](assets/Dokumentasi-SSL/1.png)
![23](assets/Dokumentasi-SSL/2.png)
![24](assets/Dokumentasi-SSL/3.png)
![25](assets/Dokumentasi-SSL/4.png)

* #### Akses aplikasi menggunakan chrome atau sejenisnya. Bisa dilihat pada aplikasi sudah secure atau sudah menggunakan https. Bisa dilihat pada pojok kiri sebelum URL aplikasi sudah terdapat gambar gembok yang artinya aplikasi sudah secure atau sudah menggunakan DNS SSL yang valid.

![26](assets/aplikasi_bisa_diakses/1.png)
![27](assets/aplikasi_bisa_diakses/2.png)
![28](assets/aplikasi_bisa_diakses/3.png)
![29](assets/aplikasi_bisa_diakses/4.png)
![30](assets/aplikasi_bisa_diakses/5.png)
![31](assets/aplikasi_bisa_diakses/6.png)


## Challenge :

### - No. 1 dibuat menjadi BASH script
![32](assets/install_docker_bash_script/1.png)

### - Buat dockerized image sekecil mungkin (front-end)
![33](assets/Dokumentasi-Docker/1.png)

### - NGINX dijalankan on top docker (No. 3)"
![34](assets/challenge_nginx_on_docker/1.png)
![35](assets/challenge_nginx_on_docker/2.png)
![36](assets/challenge_nginx_on_docker/3.png)
![37](assets/challenge_nginx_on_docker/4.png)
![38](assets/challenge_nginx_on_docker/5.png)
![39](assets/challenge_nginx_on_docker/6.png)