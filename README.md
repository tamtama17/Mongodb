# Registrasi dan Implementasi Mongodb Atlas

## Daftar isi
1. [Registrasi](#1-registrasi)
2. [Instalasi](#2-instalasi)
3. [Implementasi](#3-implementasi)
   1. [Mongo Shell](#31-mongo-shell)
   2. [MongoDB Compass](#32-mongodb-compass)
4. [Reference](#reference)

### 1. Registrasi
Hal pertama yang dilakukan adalah melakukan registrasi mongodb [disini](https://cloud.mongodb.com/user#/atlas/register/accountProfile).   
Ikuti saja langkah-langkah nya sampai cluster terbuat   
![gambar1](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar1.png "gambar1")
Jika sudah muncul tampilan seperti itu berarti cluster mongodb sudah terbuat.

### 2. Instalasi
Download dahulu [disini](https://www.mongodb.com/download-center/community), sesuaikan dengan `os` yang digunakan. Jika sudah terunduh, jalankan installernya.   
Agar bisa diakses dari mana saja, kita harus mengaturnya di `Setup connection security`, klik connect, lalu akan muncul jendela seperti ini   
![gambar2](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar4.png "gambar2")   
Tambahkan ip address yang diperbolehkan untuk mengakses cluster dan buat akun untuk meremote cluster. Jika ingin membuka cluster untuk semua koneksi, bisa menggunakan `0.0.0.0/0` yang berarti bisa diakses oleh ip siapa saja.

### 3. Implementasi
Kita akan mengakses cluster yang sudah kita buat dengan 2 cara, yaitu menggunakan Mongo Shell dan MongoDB Compass
#### 3.1 Mongo Shell
Kita akan mengimport dataset ke cluster yang sudah kita buat. Untuk kali ini dataset yang digunakan bertipe json, dataset yang digunakan kali ini bisa didapatkan [disini](https://data.world/badosa/uneces-country-overview).   
Untuk menjalankan mongodb melalui cmd, kita harus ke folder bin dimana kita menginstall mongodb. Atau jika ingin lebih fleksibel kita harus mendaftarkan `/bin` pada `PATH variable`.   
Kita harus tahu host yang akan di remote, untuk bisa mengetahuinya kita bisa lihat disini :   
![gambar3](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar7.png "gambar3")   
Syntax untuk mengimport dataset adalah seperti berikut :
```
mongoimport --host [nama host] --db [nama db] --type json --file [path menuju file dataset] --jsonArray --authenticationDatabase admin --ssl --username [username] --password [password]
```
Dengan keterangan sebagai berikut :
1. `--host` adalah nama host yang dituju
2. `--db` adalah nama database yang akan dipakai
3. `--type` adalah tipe dataset yang akan digunakan yaitu json dalam contoh kali ini
4. `--file` adalah file dataset yang akan di import
5. `--username` adalah username untuk meremote yang sudah dibuat sebelumnya
6. `--password` adalah username untuk meremote yang sudah dibuat sebelumnya

Jika menampilkan output seperti ini kemungkinan proses berhasil berjalan   
![gambar4](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar3.png "gambar4")   
Untuk mengecek apakah database sudah terbuat, kita bisa masuk terlebih dahulu dengan syntax yang bisa kita lihat di sini :   
![gambar5](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar6.png "gambar5")   
Lalu jalankan syntax ini :   
![gambar6](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar5.png "gambar6")   
Bisa dilihat file yang kita import tadi sudah masuk di database yang kita tentukan sebelumnya.
#### 3.2 MongoDB Compass
Download MongoDB Compass [disini](https://www.mongodb.com/download-center/compass), sesuaikan dengan `os`, lalu install. Copy connection string seperti gambar berikut   
![gambar7](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar10.png "gambar7")   
Lalu buka MongoDB Compass, akan otomatis mendeteksi host dan atribut lainnya. Kita tinggal memasukkan password lalu klik connect.   
![gambar8](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar8.png "gambar8")   
Kita bisa lihat, dataset yang tadi kita import juga ada disini   
![gambar9](https://github.com/tamtama17/Mongodb/blob/master/gambar/gambar9.png "gambar9")   

### Reference
- https://docs.mongodb.com/manual/
- https://www.youtube.com/watch?v=tpz-6Trd1UI
- https://docs.mongodb.com/compass/master/
- https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
