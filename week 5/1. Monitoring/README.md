# Task Monitoring Server

## monitoring - 1 CPU, 2GB RAM, 20GB Storage

![00](assets/0.png)

## 1. Deploy node exporter, prometheus & grafana on top docker

* #### Buat docker.compose.yml untuk menjalankan aplikasi node-exporter, prometheus, dan grafana.
![01](assets/1.png)
![02](assets/2.png)

* #### Up docker compose.
```
docker compose up -d
```

* #### Lalu cek apakah aplikasi sudah berjalan di docker container
```
docker ps -a
```
![03](assets/3.png)


### - Tambahkan file prometheus.yml

* #### Buat file config, lalu di dalam direktori config buat file prometheus.yml.
```
mkdir config

touch prometheus.yml
```
![04](assets/2.png)
![05](assets/4.png)


### -  Arahkan ke localhost kalian

* #### Di dalam file prometheus.yml berisi konfigurasi untuk menentukan ip dari target yang ingin di ambil data metricsnya.
![06](assets/5.png)


## 2. Buat dashboard untuk monitoring CPU & RAM

* #### Untuk membuat dashboard di grafana, pastikan dulu bahwa aplikasi node-exporter dan prometheus sudah berjalan. Dikarenakan prometheus mengambil nilai metrics dari aplikasi node-exporter, sedangkan grafana akan menampilkan dashboard bila sudah terhugung dengan aplikasi prometheus.

* #### Ini adalah tampilan dari node-exporter.
![07](assets/7.png)
![08](assets/8.png)

* #### Lalu ini adalah tampilan dari prometheus.
![09](assets/9.png)
![10](assets/10.png)
![11](assets/11.png)

* #### Jika tulisan up berarti konfigurasi yang kalian tambahkan di dalam file prometheus.yml sudah benar, jika ada tulisan down berarti pada sisi target aplikasi node-exporter belum dijalankan.

* #### Lalu ini adalah tampilan dari grafana.
![12](assets/16.png)
![13](assets/17.png)


* #### Untuk mengambil nilai dari prometheus, pada grafana tambahkan data source, lalu pilih prometheus.
![14](assets/14.png)
![15](assets/15.png)

* #### Untuk menambahkan dashboard, klik dashboard lalu klik new.

* #### Ini adalah rumus perhitungan untuk CPU Usage.
![16](assets/18.png)

* #### Sedangkan ini untuk perhitungan RAM Memory available dan total keseluruhan memory.
![17](assets/19.png)

* #### Sedangkan ini untuk melihat network receive (menerima) dan network transmit (pengiriman) data.
![18](assets/20.png)

* #### Ini adalah tampilan dashboard yang sudah dibuat.
![19](assets/21.png)
![20](assets/22.png)


## 3. Reverse proxy dan SSL :

### - node-exporter.ilham.studentdumbways.my.id
![21](assets/23.png)

### - prom.ilham.studentdumbways.my.id
![22](assets/24.png)

### - dashboard.ilham.studentdumbways.my.id
![23](assets/25.png)

* #### Untuk petunjuk pembuatan SSL certificate dengan wildcard bisa di lihat di dalam folder dns_ssl_wildcard.

## Challenge
### - Push notification grafana