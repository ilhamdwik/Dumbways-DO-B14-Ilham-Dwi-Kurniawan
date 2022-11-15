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

* #### Pilih language English. Lalu tekan Enter.
![24](assets/38.png)

* #### Pilih Continue without updating.
![25](assets/43.png)

* #### Pilih English.
![26](assets/44.png)

* #### Pilih ens33. Lalu tekan Enter.
![27](assets/45.png)

* #### Pilih edit IPv4. Tekan Enter.
![28](assets/46.png)

* #### IPv4 method,pilih yang manual.
![29](assets/47.png)

* #### Masukkan Subtet, IP Address, dll (Sesuai IP dari laptop kita masing-masing). Lalu tekan save.
![30](assets/48.png)

* #### Lalu tekan Done.
![31](assets/50.png)

* #### Untuk proxy server kosongi saja.
![32](assets/51.png)

* #### Pada tahap ini tidak perlu ada yang diubah.
![33](assets/52.png)

* #### Pilih custom storage layout.
![34](assets/53.png)

* #### Setelah itu pilih free space, pilih Add GPT Partition.
![35](assets/54.png)

* #### Isikan 2G, lalu pilih Format Swap. Lalu tekan Create.
![36](assets/55.png)

* #### Isikan size max yang tertera, untuk Format pilih ext 4, Lalu tekan Create.
![37](assets/56.png)

* #### Pastikan partition sudah terbuat, dengan mengecek MOUNT POINT beserta sizenya.
![38](assets/57.png)

* #### Klik Done.
![39](assets/58.png)

* #### Klik Continue untuk melanjutkan.
![40](assets/59.png)

* #### Isikan nama, server name, dll.
![41](assets/60.png)

* #### Klik Done.
![42](assets/61.png)

* #### Centang Install OpenSSH server.
![43](assets/62.png)

* #### Klik Done.
![44](assets/63.png)

* #### Optional pada tahap ini, semisal kalian ingin menginstal aplikasi yang tersedia bisa centang aplikasi yang ingin di install.
![45](assets/64.png)

* #### Klik Done.
![46](assets/65.png)

* #### Proses Installing kernel.
![47](assets/66.png)

![48](assets/67.png)

* #### Pilih Reboot Now.
![49](assets/68.png)

* #### Proses Reboot.
![50](assets/69.png)

* #### Login menggunakan username dan password.
![51](assets/70.png)
