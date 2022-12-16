# Task Ansible

## appserver - 1 CPU, 2GB RAM
## gateway - 1 CPU, 1GB RAM

## 20GB Storage

## 1. [Local] buat konfigurasi Ansible & dan lakukan semua setup melalui local sebanyak mungkin



## 2. [appserver] gunakan ansible-playbook
### - Membuat user baru, gunakan login ssh key
### - Instalasi Docker & node-exporter
### - Gunakan docker-compose untuk deploy aplikasi wayshub-frontend



## 3. [gateway] gunakan ansible-playbook
### - Membuat user baru, gunakan login ssh key
### - Instalasi nginx
### - Buat konfigurasi proxy lalu masukkan kedalam gateway



## 4. [monitoring] buat konfigurasi prometheus
### - monitor CPU & RAM untuk appserver
### - monitor network untuk gateway



## Challenge
## - SSL Certificate menggunakan ansible
## - Mengirimkan public key ke semua server (Note: untuk setup awal)