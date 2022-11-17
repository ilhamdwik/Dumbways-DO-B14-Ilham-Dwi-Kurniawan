# Task : Version Control System


## 1. Definisikan git menurut bahasa kalian

#### Git adalah sebuah tools untuk para developers dalam mengembangkan suatu aplikasi atau produk. dimana git ini bisa digunakan untuk menyimpan suatu file, folder, atau lainnya dan para developers bisa bekerja sama untuk mengembangkan suatu aplikasi atau produk dengan menggunakan git. karena di git ini bisa melihat siapa saja yang telah melakukan perubahan dan di file atau folder mana saja yang mengalami perubahan. 

## 2. Rubah IP address di PC kalian (tes menggunakan command ssh)

* #### Masuk ke dalam root.
![01](assets/nomer2/1.png)

* #### Dikarenakan saya memakai multipass, maka saya custom dengan membuat file test.yaml sebagai contoh.
![02](assets/nomer2/2.png)

* #### Lalu masukkan script seperti gambar di bawah ini, jangan lupa indentasi diperhatikan.
![03](assets/nomer2/3.png)

* #### Disini saat saya ssh ke ip multipass ada kendala Permission denied (publickey).
![04](assets/nomer2/4.png)


## 3. Hubungkan github ke server kalian

* #### Ketik perintah ssh-keygen, maka nanti akan secara otomatis tergenerate id_rsa dan id_rsa.pub.
![01](assets/nomer3/1.png)

* #### Coba lihat isi dari id_rsa.pub dengan menggunakan cat ./ssh/id_rsa.pub.
![02](assets/nomer3/2.png)

* #### Buka github.com/settings/keys lalu klik new ssh key.
![03](assets/nomer3/3.png)

* #### Selanjutnya copy paste key yang berada di dalam id_rsa.pub ke ssh key di github,lalu klik Add SSH key.
![04](assets/nomer3/4.png)

* #### Lalu masukkan password akun github anda.
![05](assets/nomer3/5.png)

* #### Maka proses penambahan ssh keys ke github sudah berhasil dilakukan.
![06](assets/nomer3/6.png)

* #### Coba cek koneksi device kita dengan akun github apakah sudah terkoneksi dengan baik, jika terdapat tulisan Hi <nama_akun_github>! ....., maka akun github anda sudah terhubung dengan device kalian dengan menggunakan ssh keys.
![07](assets/nomer3/7.png)

* #### Buat direktori, pada case ini saya membuat direktori dengan nama task4.
![08](assets/nomer3/8.png)

* #### Lalu masuk ke dalam direktori task4, selanjutnya inisialisasi git repository anda dengan menggunakan perintah git init. pada case saya ini, saya lupa menambahkan config username dan user email.
![09](assets/nomer3/9.png)

* #### Maka tambahkan dulu config username dan config user email dari akun github anda.
![10](assets/nomer3/10.png)

* #### Lalu cek git config --list, bila user.name dan user.email sudah terinstall, maka akan muncul seperti gambar dibawah ini.
![11](assets/nomer3/11.png)

* #### Lalu buat file.
![12](assets/nomer3/13.png)

* #### Cek dengan git status, maka akan muncul untracked files.
![13](assets/nomer3/14.png)

* #### Tambahkan file untuk di upload di github dengan perintah "git add ." command (.) titik bermaksud untuk memilih semua file yang berada di direktori task4.
![14](assets/nomer3/15.png)

* #### Buat Repository di github dengan nama task4.
![15](assets/nomer3/16.png)

* #### Maka github akan memberikan panduan setup untuk dijalankan di terminal anda.
![16](assets/nomer3/17.png)

* #### Dikarenakan tadi saya sudah menambahkan command seperti git init, git add, dan git commit terlebih dahulu, maka bisa langsung ke step selanjutnya yaitu perintah git remote add origin <link_ssh>. 
![17](assets/nomer3/18.png)

* #### Lalu masukkan perintah git push origin master, command ini bermaksud untuk mengupload file-file yang sudah kita tambahkan tadi dengan perintah git add dan git commit, perintah origin master berarti kitamengupload file-file tersebut  di dalam branch master. 
![18](assets/nomer3/19.png)

* #### Maka akan secara otomatis file-file tersebut sudah terupload di dalam repository github kita. 
![19](assets/nomer3/20.png)


## 4. Buat 3 branch untuk repository
* #### Development
* #### Staging
* #### Production

* #### Cek terlebih dahulu branch yang ad di repo kita dengan menggunakan command git branch atau git branch -a. 
![01](assets/nomer4/1.png)

* #### Untuk membuat branch baru cukup masukkan perintah git branch <nama_branch>. 
![02](assets/nomer4/2.png)

* #### Lalu cek lagi menggunakan perintah git branch atau git branch -a untuk melihat branch yang ada di repo. 
![03](assets/nomer4/3.png)

![04](assets/nomer4/4.png)


Challenge
3 command git yang belum dijelaskan

git rebase, git merge, git log, git clean