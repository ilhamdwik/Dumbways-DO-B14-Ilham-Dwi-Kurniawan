# Task : Application in Server


## 1. Perbandingan antara Monolith & Microservices

#### Aplikasi monolitik terbentuk sebagai satu kesatuan kode yang tidak dapat dipisahkan satu dan lainnya. Salah satu karakter sistem arsitektur monolitik adalah saat pemrogram ingin melakukan perubahan pada sistem monolitik, developers harus mengubah satu kesatuan kode secara menyeluruh dan bersamaan. semisal ada fitur yang tidak berjalan, maka fitur yang lainnya juga akan berhenti berjalan.

#### Jika monolitik adalah sebuah arsitektur aplikasi secara kesatuan atau tunggal, maka microservices adalah sebaliknya. Microservices terbagi menjadi beberapa unit pecahan yang lebih kecil dan spesifik. Setiap unitnya terpisah dan memiliki sistem beserta database sendiri untuk beroperasi dan menggunakan mekanisme API untuk terhubung dengan unit lainnya. bisa dibilang microservice ini setiap fitur memiliki databasenya sendiri pada setiap server, dan akan ada suatu database dan server yang lebih besar untuk menghandle semua fitur tersebut.

### Monolitik :

* #### Memiliki tim yang kecil
* #### Sistem aplikasinya sederhana
* #### Meluncurkan aplikasi lebih cepat

### Microservices :

* #### Aplikasi lebih rumit dan bertujuan untuk perluasan bisnis
* #### Memiliki tim programmer yang memadai


## 2. Deploy Aplikasi wayshub-frontend (NodeJS)

* #### Pertama clone terlebih dahulu aplikasi yang ingin kita install.
![01](assets/nomer_2/1.png)

* #### Setelah clone dari github pastikan bahwa file atau folder yang sudah kita clone berada dalam laptop atau pc kita, pada gambar di bawah sudah ada folder yang bernama wayshub-frontend.
![02](assets/nomer_2/2.png)

* #### Lalu jangan lupa untuk berpindah ke direktori wayshub-frontend.
![03](assets/nomer_2/3.png)

* #### Dikarenakan dalam proses clone, dependencies dari aplikasi masih belum terinstall, maka untuk aplikasi node js jalankan npm install, dengan command ini akan mengunduh semua dependencies yang diperlukan untuk menjalankan aplikasi tersebut sesuai apa yang tercantum di dalam package.json aplikasi tersebut.
![04](assets/nomer_2/4.png)

![05](assets/nomer_2/5.png)

* #### Setelah proses npm install coba lihat list dari folder saat ini dengan perintah ll atau ls -la, bisa dilihat pada gambar dibawah ada folder bernama node_modules yang sebelumnya tidak ada, tetapi setelah memasukkan perintah npm install maka folder tersebut akan terbuat dikarenakan semua dependencies yang diperlukan aplikasi tersebut berada dalam folder tersebut.
![06](assets/nomer_2/6.png)

* #### Untuk menjalankan aplikasi pada node js, ketikkan perintah npm start.
![07](assets/nomer_2/7.png)

* #### Setelah npm start maka akan muncul tulisan starting development program dan selanjutnya akan muncul di port berapa aplikasi yang kita jalankan berjalan, namun pada case ini port tidak muncul dikarenakan pada aplikasi ini masih ada sejumlah attention bahwa codingan atau script code dari aplikasi ini masih belum clean code atau masih ada yang perlu diperbaiki dalam script codenya, namun ini bukan error atau bug.
![08](assets/nomer_2/8.png)

* #### Setelah berjalan jika kalian ingin melihat di port yang berjalan di laptop atau PC kalian bisa dengan command netstat -nlptu untuk melihat port berapa saja yang berjalan di laptop atau PC, cari saja port dengan nama program name yang sama dengan aplikasi yang sedang kalian jalankan pada saat ini.
![09](assets/nomer_2/9.png)


## 3. Deploy Golang & Python dengan menampilkan nama masing-masing

* #### Install pm2 dengan command npm install -g pm2.
![01](assets/nomer_3/1.png)

* #### Untuk mengecek apakah sudah terinstall pm2, coba masukkan perintah pm2 list, ini akan menampilkan list program yang sudah dijalankan dengan pm2.
![02](assets/nomer_3/2.png)

* #### Masuk ke direktori dari aplikasi yang ingin dijalankan, lalu cek list file dan folder yang berada dalam aplikasi tersebut menggunakan command ll.
![03](assets/nomer_3/4.png)

* #### Untuk menjalankan aplikasi golang di pm2, pastikan sudah menjalankan build pada index.go dengan command "go build index.go", setelah membuild index.go maka akan terbuat file atau folder bernama index yang berisi data hasil build dari index.go, lalu coba jalankan ./index untuk mengetahui apakah build dari aplikasi golang sudah berjalan lancar, dalam case ini akan muncul tulisan Ilham Dwi Kurniawan setelah menjalankan ./index dikarenakan di dalam aplikasi golang saya hanya menampilkan nama saya di script code golangnya. Lalu untuk menjalankan aplikasi golang di pm2 bisa menggunakan command pm2 start ./index --name <nama_aplikasi> dan akan ditampilkan list dari aplikasi yang berjalan di pm2.
![04](assets/nomer_3/5.png)

* #### Untuk menjalankan aplikasi python di pm2, masuk ke dalam direktori aplikasi python terlebih dahulu, lalu masukkan perintah pm2 start index.py --name <nama_aplikasi> --interpreter python3, nah disini untuk menjalankan aplikasi python di pm2 dibutuhkan interpreter dari python untuk berjalan di pm2.
![05](assets/nomer_3/6.png)

* #### Lalu cek di port berapa aplikasi python berjalan menggunakan netstat -nlptu, setelah itu buka terminal yang lain untuk menjalankan localtunnel, untuk menjalankan localtunnel bisa menggunakan command lt --port <port_yang_berjalan_diaplikasi_python>, setelah itu akan muncul semacam link untuk membuka aplikasi tersebut. 
![06](assets/nomer_3/7.png)

* #### Lalu copy paste ke browser kalian link tersebut. Jika muncul tulisan Continue, maka klik saja tombol Continue tersebut.
![07](assets/nomer_3/8.png)

* #### Untuk menjalankan aplikasi nodejs di pm2 kurang lebih sama seperti aplikasi python dan golang dengan menjalankan perintah pm2 start index.js --name <nama_aplikasi> -- start. lalu cek dimana port berjalan.
![08](assets/nomer_3/9.png)

* #### Lalu cek dimana port berjalan, kemudian akses menggunakan ip dari multipass ditambah port tersebut berjalan.
![09](assets/nomer_3/10.png)

* #### Ini adalah proses deploy aplikasi wayshub-frontend di pm2.
![10](assets/nomer_3/11.png)

![11](assets/nomer_3/12.png)

![12](assets/nomer_3/13.png)


## 4. Jalankan localtunnel untuk aplikasi no 1

* #### Jalankan perintah sudo apt install curl.
![01](assets/nomer_4/1.png)

* #### Lalu jalankan perintah seperti pada gambar di bawah ini.
![02](assets/nomer_4/2.png)

* #### Lalu install nvm 14.
![03](assets/nomer_4/3.png)

* #### Cek versi node js dan npm.
![04](assets/nomer_4/4.png)

* #### Lalu install localtunnel dengan perintah npm install -g localtunnel, -g artinya kita menginstall secara global dan akan bisa diakses di dalam direktori manapun di dalam laptop atau pc kita.
![05](assets/nomer_4/5.png)

* #### Jangan lupa untuk selalu menjalankan npm install terlebih dahulu setelah meng-clone dari github lalu npm start. Agar aplikasi kita bisa diakses secara publik melalui internet dengan menggunakan localtunnel, jalankan terlebih dahulu aplikasi kita menggunakan npm start, lalu buka terminal baru dan masukkan perintah lt --port <port_yang_berjalan_diaplikasi_tersebut>.
![06](assets/nomer_4/6.png)

* #### Setelah menjalankan perintah lt --port <port_yang_berjalan_diaplikasi_tersebut> maka akan muncul link untuk mengakses aplikasi tersebut lewat internet. Copy paste link tersebut ke dalam browser.
![07](assets/nomer_4/7.png)

* #### Lalu Click to Continue.
![08](assets/nomer_4/8.png)

* #### Maka aplikasi tersebut sudah bisa diakses melalui internet.
![09](assets/nomer_4/9.png)


## Challenge
### Gunakan PM2

### Repository : https://github.com/dumbwaysdev/wayshub-frontend
