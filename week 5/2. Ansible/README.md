# Task Ansible

## appserver - 1 CPU, 2GB RAM
## 20GB Storage
![00](assets/0.png)

## gateway - 1 CPU, 1GB RAM
## 20GB Storage
![01](assets/1.png)


## 1. [Local] buat konfigurasi Ansible & dan lakukan semua setup melalui local sebanyak mungkin

![01](assets/6.png)


## 2. [appserver] gunakan ansible-playbook

### - Membuat user baru, gunakan login ssh key

* #### Buat ansible-playbook bernama create_user_and_deploy_ssh_key.yml. Disini saya membuat user baru bernama "ilham" pada sisi appserver.
![02](assets/create_user_and_login_ssh_key/appserver/1.png)

* #### Buat file Inventory.
![03](assets/create_user_and_login_ssh_key/appserver/2.png)

* #### Buat file ansible.cfg.
![04](assets/create_user_and_login_ssh_key/appserver/3.png)

* #### Cek sintax dari ansible-playbook. Lalu jalankan ansible-playbook.
```
ansible-playbook nama_file --syntax-check

lalu

ansible-playbook nama_file
```

![05](assets/create_user_and_login_ssh_key/appserver/4.png)

* #### Lalu cek pada sisi appserver apakah user ilham sudah terbuat. Dan cek juga pada folder .ssh/authorized_key apakah sudah ditambahkan kunci publik dari server yang telah me-remote server appserver.
![06](assets/create_user_and_login_ssh_key/appserver/5.png)

* #### Lalu coba untuk ssh ke dalam user yang telah kita buat di dalam server appserver. Dan pastikan kita tidak perlu memasukkan password untuk login sshnya.
![07](assets/create_user_and_login_ssh_key/appserver/6.png)


### - Instalasi Docker & node-exporter

### Install Docker
* #### Pertama tambahkan plugin di dalam server local kita.
![08](assets/installasi_docker/1.png)

* #### Lalu buat file docker.yml di dalam server local kita.
![09](assets/installasi_docker/2.png)
![10](assets/installasi_docker/3.png)

* #### Lalu cek sintax ansible-playbook dan jalankan ansible-playbook.
![11](assets/installasi_docker/4.png)

* #### Lalu cek pada sisi server appserver apakah docker sudah terinstall.
![12](assets/installasi_docker/5.png)


### Install Node Exporter

* #### Buat file install_node_exporter.yml di dalam server local kita.
![13](assets/install_node_exporter/1.png)

* #### Lalu cek sintax ansible-playbook dan jalankan ansible-playbook.
![14](assets/install_node_exporter/2.png)

* #### Lalu cek pada sisi server appserver apakah node-exporter sudah terdeploy dan berjalan.
```
docker ps -a
```
![15](assets/install_node_exporter/3.png)

* #### Lalu akses pada web menggunakan ip publik dari server appserver lalu tambahkan port yang berjalam di node-exporter.
![16](assets/install_node_exporter/4.png)


### - Gunakan docker-compose untuk deploy aplikasi wayshub-frontend

* #### Buat list directory seperti ini.
![17](assets/deploy_wayshub_frontend/1.png)

* #### Isi dari file deploy_wayshub_frontend.yml.
![18](assets/deploy_wayshub_frontend/2.png)

* #### Isi dari file docker-compose.yml.
![19](assets/deploy_wayshub_frontend/3.png)

* #### Cek sintax dan jalankan ansible-playbook.
![20](assets/deploy_wayshub_frontend/4.png)

* #### Cek wayshub di web browser.
![21](assets/deploy_wayshub_frontend/5.png)

![22](assets/deploy_wayshub_frontend/6.png)


## 3. [gateway] gunakan ansible-playbook

### - Membuat user baru, gunakan login ssh key

* #### Buat ansible-playbook bernama create_user_and_deploy_ssh_key.yml. Disini saya membuat user baru bernama "ilham2" pada sisi gateway.
![23](assets/create_user_and_login_ssh_key/gateway/1.png)

* #### Buat file Inventory.
![24](assets/create_user_and_login_ssh_key/gateway/2.png)

* #### Buat file ansible.cfg.
![25](assets/create_user_and_login_ssh_key/gateway/3.png)

* #### Cek sintax dari ansible-playbook. Lalu jalankan ansible-playbook.
```
ansible-playbook nama_file --syntax-check

lalu

ansible-playbook nama_file
```

![26](assets/create_user_and_login_ssh_key/gateway/4.png)

* #### Lalu cek pada sisi gateway apakah user ilham2 sudah terbuat. Dan cek juga pada folder .ssh/authorized_key apakah sudah ditambahkan kunci publik dari server yang telah me-remote server gateway.
![27](assets/create_user_and_login_ssh_key/gateway/5.png)

* #### Lalu coba untuk ssh ke dalam user yang telah kita buat di dalam server appserver. Dan pastikan kita tidak perlu memasukkan password untuk login sshnya.
![28](assets/create_user_and_login_ssh_key/gateway/6.png)


### - Instalasi nginx

![29](assets/2.png)

![30](assets/3.png)


### - Buat konfigurasi proxy lalu masukkan kedalam gateway

![31](assets/2.png)

![32](assets/4.png)

![33](assets/5.png)


## 4. [monitoring] buat konfigurasi prometheus

### - monitor CPU & RAM untuk appserver

* #### Tambahkan IP target yang ingin di monitoring.
![34](assets/monitoring/1.png)

![35](assets/monitoring/2.png)

![36](assets/monitoring/3.png)

### - monitor network untuk appserver
![37](assets/monitoring/4.png)

### - monitor network untuk gateway
![38](assets/monitoring/5.png)


## Challenge

## - SSL Certificate menggunakan ansible

## - Mengirimkan public key ke semua server (Note: untuk setup awal)

* #### Buat file add_public_key.yml.
![39](assets/public_key_ansible/1.png)

* #### Buat file Inventory.
![40](assets/public_key_ansible/2.png)

* #### Buat file ansible.cfg.
![40](assets/public_key_ansible/7.png)

* #### Cek authorized_keys dan belum ada isinya.
![41](assets/public_key_ansible/3.png)

* #### Pada saat menjalankan ansible-playbook disini saya menambahkan --ask-pass dikarenakan pada file add_public_key.yml saya belum menambahkan variabel password dari server yang mau di remote. variabel --ask-pass akan meminta password saat akan menjalankan ansible-playbook.
![42](assets/public_key_ansible/4.png)

* #### Lalu cek lagi authorized_keys yang ada pada server yang sudah di remote tadi. Maka authorized_keys secara otomatis ditambahkan.
![43](assets/public_key_ansible/5.png)

* #### Lalu coba ssh ke dalam server, maka tidak memerlukan password dikarenakan kita sudah menambahkan public_key lewat ansible_playbook.
![44](assets/public_key_ansible/6.png)