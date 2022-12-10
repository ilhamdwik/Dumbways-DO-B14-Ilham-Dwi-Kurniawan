# Stage 2 Day 6 | CI/CD : Jenkins

## "CICD - 2 CPU, 2GB RAM, 20GB Storage

## 1. Jalankan Jenkins on top Docker

![00](assets/26.png)

![01](assets/1.png)

![02](assets/2.png)

![03](assets/3.png)

![04](assets/4.png)

![05](assets/5.png)

![06](assets/6.png)

![07](assets/7.png)

* #### Masukkan private key dari file di dalam server. Masuk ke direktori .ssh, lalu copy id_rsa, paste ke dalam global credentials key di dalam jenkins.
![08](assets/8.png)

![09](assets/9.png)

![10](assets/10.png)

* #### Kelompok kami menggunakan repository private.
![11](assets/11.png)
![12](assets/12.png)

![13](assets/13.png)

* #### Dikarenakan kelompok kami menggunakan repository private. Maka repository URL kita masukkan menggunakan ssh.
![14](assets/14.png)

![15](assets/15.png)

* #### Agar jenkins bisa mengetahui jika ada update di repository kita maka aktifkan webhooks di dalam repository github. Isi payload url.
```
link_url_jenkins/github-webhook/
```
![16](assets/16.png)

![17](assets/17.png)

![18](assets/18.png)

* #### Lalu pilih Recent Deliveries, jika sudah berwarna hijau maka jenkins dan webhook github sudah terhubung dan akan melakukan build secara otomatis jika ada perubahan di repository kita.
![19](assets/19.png)

![20](assets/20.png)

![21](assets/21.png)

![22](assets/22.png)


## 2. Pipeline untuk frontend & backend

![23](assets/27.png)
![24](assets/28.png)
![25](assets/29.png)
![26](assets/30.png)
![26](assets/25.png)


## 3. Reverse Proxy & SSL Certificate untuk domain jenkins
![11](assets/26.png)


## Challenge
### - Repository Private

* #### Jika repository menggunakan private, maka pada saat membuat jobs di jenkins kita hanya bisa memasukkan link url repository menggunakan ssh.
![11](assets/11.png)
![12](assets/12.png)
![11](assets/19.png)
![12](assets/20.png)

### - Auto-Trigger build pipeline setiap push di github

* #### Jika ada tanda hijau dan tulisan push, maka github melakukan push dan jenkins melakukan update secara otomatisatau build otomatis.
![11](assets/19.png)
![12](assets/22.png)

### - Push Notification melalui discord, telegram atau app pilihan kalian"

![24](assets/31.png)
![25](assets/32.png)
![26](assets/33.png)