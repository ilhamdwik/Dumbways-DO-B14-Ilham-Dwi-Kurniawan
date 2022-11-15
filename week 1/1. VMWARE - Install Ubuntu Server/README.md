# Task : Introduction to DevOps

### 1. Definisi DevOps

DevOps merupakan singkatan dari dua kata yaitu Development dan Operation.

Di mana kedua kata tersebut bermakna menggabungkan proses development (pengembangan) dari sebuah sistem/aplikasi dengan operation (operasional). DevOps adalah sebuah prinsip developer untuk mengkoordinasikan antar tim yaitu tim development dengan tim operations dengan efektif dan efisien.

### 2. Sebutkan 2 lifecycle DevOps & jelaskan definisinya

- Plan (tahap perencanaan) : pada tahap ini sebelum memulai membangun sebuah aplikasi kita harus melakukan perencanaan terlebih dahulu. Dikarenakan segala sesuatu yang dimulai tanpa adanya perencanaan terlebih dahulu bisa terjadi ketidak sesuain dalam membangun sebuah aplikasi. Contohnya bila tidak ada perencanaan : waktu pembangunan sebuah aplikasi tidak tepat waktu, biaya (cost) yang dikeluarkan untuk pembangunan aplikasi bisa membengkak, ketidaksesuaian aplikasi yang setelah dibuat oleh tim developer.

- Code  : pada tahap ini development team akan bekerja untuk membangun sebuah aplikasi yang sudah direncanakan sebelumnya. Pada tahap ini perlu adanya kerjasama yang baik antara tim development dengan tim operation agar nantinya aplikasi yang sudah dibuat bisa berjalan dengan baik.

- Deploy : pada tahap ini tim operation akan bekerja untuk mendeploy aplikasi yang sudah dibangun oleh tim development. Proses deployment juga butuh waktu untuk proses installasi dibagian server dan perlunya perhitungan spek yang dibutuhkan pada bagian server agar aplikasi tidak terbebani setelah di deploy.


### 3. Installasi Ubuntu Server

1 CPU, 2GB RAM & 20GB Storage ( 2GB digunakan utk swap )
setup IP Static
Install OpenSSH server


* #### Kunjungi situs vmware.com seperti gambar dibawah ini. Lalu pilih download for windows atau linux sesuai dengan OS yang digunakan.
![01](assets/1.png)

* #### Lalu klik Next.
![02](assets/2.png)

* #### Centang I accept the terms..., lalu Next.
![03](assets/3.png)

* #### Pilih yang bawah Add VMware Workstation..., lalu Next.
![04](assets/4.png)

* #### Centang keduanya seperti gambar dibawah ini, lalu Next.
![05](assets/5.png)

* #### Semisal setelah install ingin memunculkan icon dari VMware bisa centang Desktop, lalu Next
![06](assets/6.png)

* #### Klik Install.
![07](assets/7.png)

* #### Proses Installing VMware sedang berjalan.
![08](assets/8.png)

* #### Semisal mempunyai License, bisa klik License, kalau tidak bisa langsung klik Finish.
![09](assets/9.png)

* #### Ini tampilan semisal anda ingin memasukkan license key.
![10](assets/10.png)

* #### Buka Home di windows lalu ketik VMware Workstation Player, jika muncul berarti proses installasi berjalan dengan baik.
![11](assets/11.png)

* #### Tampilan setelah dibuka VMware Workstation Player. Pilih Create a New Virtual Machine.
![12](assets/12.png)

* #### Pilih Browse untuk memilih file iso yang akan digunakan. Lalu Next.
![13](assets/28.png)

* #### Masukkan Fullname, username, dll. Lalu Next.
![14](assets/29.png)

* #### Klik Next.
![15](assets/30.png)

* #### Maximum disk size isi 20.0. Lalu pilih Split virtual disk intomultiple files. Lalu Next.
![16](assets/31.png)

* #### Pilih Customize Hardware.
![17](assets/21.png)

* #### Memory isikan 2GB.
![18](assets/32.png)

* #### Processors isikan 1 (Optional) diatas 1 juga gpp sesuai kebutuhan masing-masing.
![19](assets/33.png)

* #### Network Adapter ubah menjadi bridged.
![20](assets/34.png)

* #### Klik Finish.
![21](assets/35.png)

* #### Proses Installasi.
![22](assets/36.png)
![23](assets/37.png)
