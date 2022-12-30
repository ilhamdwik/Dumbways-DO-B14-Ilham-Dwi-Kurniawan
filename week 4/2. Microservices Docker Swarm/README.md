# Stage 2 Day 5 | Microservices : Docker Swarm

## "worker - 1 CPU, 1GB RAM, 20GB Storage

## 1. Deploy aplikasi frontend dalam Docker Swarm
![01](assets/1.png)

## 2. Hubungkan worker dengan appserver

* #### Menghubungkan vm Apserver dengan vm worker.
```
docker swarm init --advertise-addr (ip_appserver)
``` 
![02](assets/3.png)

* #### Copy paste tulisan docker swarm join yang muncul pada ssat docker swarm init di dalam vm worker.
```
docker swarm join --token .......
``` 
![03](assets/4.png)

* #### Pada vm appserver coba cek apakah vm worker sudah terhubung sebagai worker.
```
docker node ls
``` 
![04](assets/5.png)

## 3. Jalankan 2 replica untuk aplikasinya

* #### Untuk menjalankan Replica ketikkan perintah seperti dibawah. 2 adalah jumlah replica.
```
docker service scale (nama_service)=2
``` 
![05](assets/6.png)

## 4. Web dapat diakses melalui Docker Swarm

* #### Untuk capture saat mengakses aplikasi kita lupa untuk mencapturenya, jadi untuk capture aplikasi mungkin hanya ini yang bisa ditampilkan, namun dari kelompok kami aplikasi sudah bisa diakses dan dijalankan menggunakan ip server dan ip worker.
![06](assets/2.png)


## Note :
### - Matikan service jika sudah didokumentasi
### - Praktekkan kembali pada saat presentasi"

		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
