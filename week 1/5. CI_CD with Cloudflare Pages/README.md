# Task : CI/CD with Cloudflare Pages


## 1. Definisikan CI/CD sesuai dengan bahasa kalian

* #### CI/CD adalah rangkaian praktik pengembangan perangkat lunak secara otomatis yang memungkinkan developer untuk menerapkan perubahan yang lebih sering pada perangkat lunak yang dikembangkan.

* #### CI adalah praktik pengembangan perangkat lunak yang dilakukan developer dengan menggabungkan serangkaian kode yang terintegrasi ke dalam sebuah repository secara berkelanjutan. 

* #### Pada tahap Continuous Delivery, kode-kode terintegrasi yang telah dibuat dari tahap CI akan secara otomatis dikirim ke suatu lingkungan untuk melakukan uji kelayakan pada software tersebut. Apabila hasil pengujian otomatis tersebut telah berhasil, maka perangkat lunak tersebut telah layak untuk diproduksi. 

* #### Setelah melalui proses uji kelayakan pada bagian Continuous Delivery, proses selanjutnya dari pengembangan perangkat lunak menggunakan CI/CD adalah Continuous Deployment. Pada tahap ini perangkat lunak yang telah diperbaharui akan disebarkan ke tahap produksi. 


## 2. Fork repository Dumbflix

* #### Pertama masuk ke github dari repository yang ingin di fork. Pada kasus ini saya akan fork dari repository berikut : https://github.com/dumbwaysdev/dumbflix-frontend.
![01](assets/tugas2/1.png)

* #### Selanjutnya klik fork yang ada di pojok kanan atas bagian github. Lalu pilih "Create a new fork".
![02](assets/tugas2/2.png)

* #### Selanjutnya akan muncul halaman github seperti gambar di bawah, masukkan nama repository sesuai keinginan kalian. Lalu klik "Create fork".
![03](assets/tugas2/3.png)

* #### Maka akan secara otomatis repository yang kalian fork menjadi repository milik kalian. Coba cek di repository akun github kalian.
![04](assets/tugas2/4.png)

* #### Fork repository dari dumbflix-frontend telah berhasil.
![05](assets/tugas2/5.png)


## 3. Deploy melalui Cloudflare Pages

* #### Pastikan kalian sudah melakukan register ke https://cloudflare.com, Jika kalian belum mempunyai akun Cloudflare kalian bisa melakukan registrasi terlebih dahulu.
![01](assets/tugas3/1.png)

* #### Jika sudah melakukan registrasi, akan muncul halaman awal cloudflare seperti gambar di bawah.
![02](assets/tugas3/2.png)

* #### Masuk ke "Pages" lalu verifikasi akun gmail kalian.
![03](assets/tugas3/3.png)

* #### Selanjutnya klik "Connect to git", Supaya repository di akun github kalian terdeteksi ke Cloudflare Pages.
![04](assets/tugas3/4.png)

* #### Lalu akan muncul halaman seperti gambar di bawah. klik "Install and Authorize".
![05](assets/tugas3/5.png)

![06](assets/tugas3/6.png)

* #### Akun github akan terhubung dengan akun cloudflare kalian.
![07](assets/tugas3/7.png)

* #### Pilih repository yang ingin kalian deploy.
![08](assets/tugas3/8.png)

* #### Lalu klik "Begin setup".
![09](assets/tugas3/9.png)

* #### Isi nama projek dan branch yang kalian gunakan.
![10](assets/tugas3/10.png)

* #### Dikarenakan saya akan men-deploy aplikasi dari frontend, maka di framework preset saya pilih "CreateReact App", Build command dan build output directory tidak perlu diubah pada kasus ini.
![11](assets/tugas3/11.png)

* #### Klik "Save and Deploy".
![12](assets/tugas3/12.png)

* #### Maka cloudflare akan secara otomatis men-deploy aplikasi kalian. Pada gambar di bawah adalah proses deploy aplikasi.
![13](assets/tugas3/13.png)

![14](assets/tugas3/14.png)

* #### Jika pada kolom Status Success, maka aplikasi kalian sudah ter-deploy.
![15](assets/tugas3/15.png)

![16](assets/tugas3/16.png)

* #### Lalu klik di halaman "Pages". Lalu pada kolom Domain adalah url dari aplikasi yang sudah kalian deploy. Copy paste link tersebut lalu buka di browser kalian.
![17](assets/tugas3/17.png)

* #### Jika berhasil maka aplikasi kalian sudah ter-deploy dan bisa diakses di internet.
![18](assets/tugas3/18.png)

* #### Selanjutnya coba ubah script code yang ada di dalam folder public/index.html. COba ubah Fadil Darma Putera Z menjadi nama kalian masing-masing.
![19](assets/tugas3/19.png)

![20](assets/tugas3/20.png)

* #### Lalu simpan perubahan dengan klik "Commit changes".
![21](assets/tugas3/21.png)

* #### Maka pada akun cloudflare akan secara otomatis men-deploy ulang aplikasi yang sudah kita deploy sebelumnya. Dikarenakan cloudflare sudah menggunakan konsep CI/CD, sehingga jika terjadi perubahan atau update dari repository github yang sudah kalian deploy di cloudflare akan otomatis men-deploy ulang.
![22](assets/tugas3/22.png)

![23](assets/tugas3/23.png)

![24](assets/tugas3/24.png)

* #### Jika Status sudah berubah dari in progress menjadi success, maka aplikasi kalian sudah ter-update sesuai perubahan yang terjadi di repository kalian.
![25](assets/tugas3/25.png)

* #### Maka bisa dilihat title yang awalnya bernama Fadil Darma Putera Z berubah menjadi Ilham Dwi Kurniawan.
![26](assets/tugas3/26.png)


### Challenge
### Deploy 2 branch yang berbeda

* #### Untuk men-deploy dengan 2 branch yang berbeda. Pertama buat dulu branch baru di akun github kalian. Untuk membuat branch baru klik master lalu klik "view all branch".
![01](assets/challenge/1.png)

* #### Pilih new branch.
![02](assets/challenge/2.png)

* #### Masukkan nama branch yang kalian inginkan. Lalu klik Create branch.
![03](assets/challenge/3.png)

* #### Maka akan ada 2 branch berbeda di repository kalian.
![04](assets/challenge/4.png)

* #### Pada akun cloudflare akan otomatis menjalankan perubahan di aplikasi kalian. Bisa dilihat bahwa branch yang sudah ditambahkan di github, maka di cloudflare juga otomatis berubah.
![05](assets/challenge/5.png)

![06](assets/challenge/6.png)

![07](assets/challenge/7.png)

* #### Lalu lihat di All deployment ada Source dengan nama staging, lalu buka link URL yang ada di kolom Deployment.
![08](assets/challenge/8.png)

* #### Maka akan muncul hasil deploy menggunakan branch staging.
![09](assets/challenge/9.png)

* #### Untuk melihat perbedaan dari hasil deploy menggunakan 2 branch yang berbeda. Saya ubah file di index.html. Title saya ubah menjadi Dumbflix - master - Ilham Dwi Kurniawan pada branch master.
![10](assets/challenge/10.png)

* #### Lalu buka perubahan apa yang terjadi di branch master.
![11](assets/challenge/11.png)

* #### Maka akan terubah titlenya menjadi Dumbflix - master - Ilham Dwi Kurniawan.
![12](assets/challenge/12.png)

* #### Saya ubah file di index.html. Title saya ubah menjadi Dumbflix - staging - Ilham Dwi Kurniawan pada branch staging.
![13](assets/challenge/13.png)

![14](assets/challenge/14.png)

* #### Maka akan otomatis ter-update.
![15](assets/challenge/15.png)

![16](assets/challenge/16.png)

* #### Lalu buka link URL dari branch staging.
![17](assets/challenge/17.png)

* #### Domain dari branch master.
![18](assets/challenge/18.png)

* #### Domain dari branch staging.
![19](assets/challenge/19.png)


### Repo Dumbflix
### https://github.com/dumbwaysdev/dumbflix-frontend