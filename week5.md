# Writing Week 5, 24 - 28 Oktober 2022)

## Backend Development
---
### Web Server & RESTful API
---
#### Pengertian Web Server
---
Web server adalah suatu perangkat lunak yang memiliki fungsi sebagai penerima permintaan yang dikirimkan oleh browser lalu memberikan tanggapan atas permintaan tersebut dalam bentuk halaman situs web atau yang biasa juga disebut dengan dokumen HTML.

Namun sebenarnya web server dapat memiliki dua definisi yang berbeda, jika dilihat dari sudut pandang sebagai bagian dari perangkat keras (hardware) dan dari sudut pandang sebagai bagian dari perangkat lunak (software).
Web server terdiri dari 2 komponen penting:
- Hardware : web server memiliki fungsi untuk digunakan sebagai penyimpanan semua data HTML dokumen, gambar, file CSS stylesheets, dan file JavaScript
- Software : fungsi dari web server adalah digunakan sebagai pusat kontrol untuk memproses seluruh permintaan yang diterima dari browser.

setiap kali browser membutuhkan file yang di-host di server web, browser meminta file melalui HTTP. Ketika permintaan mencapai server web (perangkat keras) yang benar, server HTTP (perangkat lunak) menerima permintaan tersebut, menemukan dokumen yang diminta, dan mengirimkannya kembali ke browser, juga melalui HTTP.


![web server](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server/web-server.svg)

#### Static & Dynamic Web Server
---
- Situs web statis adalah web yang mudah dalam proses pengembangan karena tidak memerlukan fungsi-fungsi yang kompleks. Tapi web statis juga punya kekurangannya sendiri. Problem utama pada web statis adalah apabila si pemilik web ingin memperbarui konten yang ada di dalam webnya. Pemilik web harus merombak isi kodenya untuk bisa memperbarui isi kontennya
- Situs web dinamis berarti bahwa server memproses konten atau bahkan membuatnya dengan cepat dari database. Pendekatan ini memberikan lebih banyak fleksibilitas, tetapi tumpukan teknis lebih kompleks, sehingga secara dramatis lebih menantang untuk membangun situs web.

#### Server Side Programming
---
Server Side Programming Language, atau Bahasa Pemrograman sisi server, adalah bahasa pemrograman web, yang letak source code nya nanti hanya ada di webserver. Bahasa ini source code nya tidak akan muncul di sisi client (browser). Client/browser hanya menerima keluaran dari kode program tersebut.

Bahasa yang biasa digunakan pada server side programming 
- Python
- Node.js
- PHP
- Java
- Golang
- Ruby

Kelebihan Server-Side :
- Data lebih aman.
- Susah untuk ditiru karena script di jalankan di server.
- Lapisan keamanan berlapis-lapis.

Kekurangan Server-Side :
- Memerlukan Server untuk menjalankannya.
- Menambah beban kerja server.
- Agak lambat jika dibandingkan dengan Client-Side Scripting karena script diterjemahkan di - Server kemudian ditampilkan ke browser client.
#### RESTful API
---
API RESTful adalah antarmuka yang digunakan oleh dua sistem komputer untuk bertukar informasi secara aman melalui internet. Antarmuka Program Aplikasi (API) menentukan aturan yang harus Anda ikuti untuk berkomunikasi dengan sistem perangkat lunak lain.

Ini adalah langkah umum untuk semua panggilan API REST:

- Klien mengirimkan permintaan ke server. Klien mengikuti dokumentasi API untuk memformat permintaan dalam format yang dipahami oleh server.
- Server mengautentikasi klien dan mengonfirmasi bahwa klien memiliki hak untuk membuat permintaan.
- Server menerima permintaan dan memproses secara internal.
- Server mengembalikan respons kepada klien. Respons berisi informasi yang memberitahu klien jika permintaannya berhasil. Respons juga termasuk informasi apa saja yang diminta klien.

Metode :
- GET
- POST 
- PUT
- DELETE

Header HTTP
Header permintaan adalah pertukaran metadata antara klien dan server. Misalnya, header permintaan menunjukkan format permintaan dan respons, memberikan informasi tentang status permintaan, dan sebagainya.


### Intro Node.Js
---
Node.js adalah runtime environment untuk JavaScript yang bersifat open-source dan cross-platform. Dengan Node.js kita dapat menjalankan kode JavaScript di mana pun, tidak hanya terbatas pada lingkungan browser.

Node.js juga menyediakan banyak library/module JavaScript yang membantu menyederhanakan pengembangan aplikasi web.

#### Fundamental
---
Di Node, saat sistem file membaca file, Node menggunakan waktu idle untuk menangani permintaan lain. Ketika sistem file selesai, cukup pintar untuk memberi tahu Node untuk datang mengambil sumber daya dan mengirim ke browser. Ini dimungkinkan karena Node's ```event loop```.

![node js](https://miro.medium.com/max/828/1*fBOm10njasRdooZsSHXkGw.png)
Node js membawa kita ke ```callbacks```. Mereka pada dasarnya adalah fungsi yang diteruskan ke fungsi lain sebagai argumen dan dipanggil ketika kondisi tertentu terjadi.

Jadi apa yang dilakukan pengembang NodeJs pada dasarnya adalah menulis event handler yang dipanggil ketika event Node tertentu terjadi.

#### Cara Install NodeJS
---
- buka web https://nodejs.org dan download filenya sesuai OS 
- buka file yang sudah di download
- lalu klik next sampai ada tombol install
- tunggu hingga selesai dan finish

nanti kalau sudah selesai install akan bisa dicek di cmd dengan mengetikkan
```node -v ```, di laptop saya muncul hasil ```v16.18.0 ```, yang berarti nodeJS sudah berhasil terinstall

#### Penggunaan Web Server dengan NodeJS
---
- Buat folder baru, cd ke dalam folder dengan terminal atau command prompt Anda.
- Lakukan ```npm init```,tekan enter sampai Anda berhasil membuat ```package.json``` file di root folder.
- Buat ```server.js``` file di folder root, lalu masukkan kode di bawah ini l
```
//server.js
const http = require('http'),
      server = http.createServer();

server.on('request',(request,response)=>{
   response.writeHead(200,{'Content-Type':'text/plain'});
   response.write('Hello world');
   response.end();
});

server.listen(3000,()=>{
  console.log('Node server created at port 3000');
});
```
- lalu di terminal vscode, ketik ```node server.js``` dan tekan enter.lalu akan muncul output
```
node server.js 
// Server node dimulai pada port 3000
```
- Buka browser lalu ketikkan ```localhost:3000``` . akan muncul pesan Hello world .


### Express Js
---
#### Pengertian Express Js
---
Express.js adalah framework web app untuk Node.js yang ditulis dengan bahasa pemrograman JavaScript. Framework open source ini dibuat oleh TJ Holowaychuk pada tahun 2010 lalu.
Express.js adalah framework back end. Artinya, ia bertanggung jawab untuk mengatur fungsionalitas website, seperti pengelolaan routing dan session, permintaan HTTP, penanganan error, serta pertukaran data di server. 
Express JS (Model View Controller). Dengan begitu, setiap data diolah pada Model, dihubungkan melalui Controller, lalu ditampilkan menjadi informasi melalui View.

cara install express js bisa dilakukan dengan mengetikkan kode di bawah ini pada terminal project kita
```
npm install express
```

- Install nodemon
Terdapat beberapa module yang perlu diinstal untuk mempermudah develop server side application, seperti nodemon (agar dapat restart application otomatis selama proses development)

dapat diinstall dengan cara mengetikkan kode di terminal projek kita
```
npm install nodemon
```

- Penggunaan Express
---
di bawah ini contoh basic syntax express js
```
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```
pada ```localhost:3000/``` akan muncul pesan ```Hello World!```


- Basic routing express js

Routes adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan
Cara kerja routing di Express.js adalah dengan sebuah metode bernama app. Metode tersebut akan merespons setiap permintaan berbentuk HTTP. Misalnya GET, POST, PUT, dan DELETE.

contoh routing :
- Respond Hello World! pada halaman
```
app.get('/', (req, res) => {
  res.send('Hello World!')
})
```
- Respond to POST request on the root route (/)
```
app.post('/', (req, res) => {
  res.send('Got a POST request')
})
```
- Respond to a PUT request to the /user root
```
app.put('/user', (req, res) => {
  res.send('Got a PUT request at /user')
})
```
- Respond to a DELETE request to the /user root
```
app.delete('/user', (req, res) => {
  res.send('Got a DELETE request at /user')
})
```

#### Middleware
---
Middleware adalah fungsi yang digunakan untuk mengakses permintaan object (req), respons object (res), dan setiap siklus permintaan dan respon tersebut (next).
Pada Express.js, cara kerja Middleware adalah dengan mengeksekusi setiap skrip, membuat perubahan terhadap permintaan dan respons object, mengakhiri siklus permintaan-respons, lalu menyiapkan Middleware untuk siklus berikutnya.

contoh syntax Middleware :
```
var express = require('express')
var app = express()
 
app.get('/', function (req, res) {
  res.send('Hello World!')
})
 
app.listen(3000)
```

#### Backend Aplication
---
Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API
- RESTful API
RESTful API / REST API : merupakan penerapan dari API (Application Programming Interface). 
Sedangkan REST (Representional State Transfer) adalah sebuah arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi. Dengan tujuannya untuk menjadikan sistem memiliki performa yang baik, cepat dan mudah untuk di kembangkan (scale) terutama dalam pertukaran dan komunikasi data.

komponen RESTful API :
- URL Design
- HTTP Verbs
- HTTP Response Code 
- Format Response

contoh RESTful API :
```
POST http://localhost:5000/list-todo
# menambahkan data pada tabel
Content-Type: application/json

{
    "item": "Kuliahh",
    "kondisi": "mendadak",
    "deadline": "20/09/2090"
}
```
### Design Database with MySQL 
---
Dalam membuat basis data seorang analis harus menganalisa terlebih dahulu Entitas yang dibutuhkan dalam tabel yang akan dibuat. Setelah itu akan membentuk ERD.
Entitas bisa dikatakan adalah yang mewakili objek yang ada dan bersifat unik sedangkan ERD singkatan dari Entity Relathionship Diagram yang akan menggambarkan entitas dalam bentuk simbol serta menentukan tipe dari entitas lengkap dengan atributnya. Bisa dikatakan entitas akan menjadi / mewakili nama tabel yang akan dibuat.
Masing-masing entitas mempunyai lebih dari satu atribut.

Ada beberapa langkah yang dapat dilakukan untuk menemukan entitas sebagai berikut :
- Membuat alur cerita atau ilustrasi (role of bussiness) tentang sistem yang akan dibuat    
- Tandai sebagai objek setiap ada kaya benda dalam cerita tersebut
- Yakinkan bahwa nantinya objek tersebut memiliki karakteristik atau atribut
- Jika dia memiliki atribut tandai dia sebagai entitas
- Gambarkan entitas dalam bentuk diagram menggunakan simbol yang sudah ditetapkan

contoh Studi Kasus :
Sekolah ABC memiliki 634 siswa dan guru + pegawai 43 orang. Petugas perpustakaan yang menangani setiap kegiatan yang terjadi pada perpustakaan. Kegiatan petugas meliputi peminjaman, pengembalian, pencatatan buku masuk, pembuatan seri buku pencatatan sanksi jika buku hilang atau rusak. Jika siswa dan guru meminjam buku dapat langsung meminjam ke petugas perpustakaan. Siswa dan guru dapat mencari stok ketersediaan buku pada mesin pencarian. Rak buku disusun berdasarkan jenis buku. Peminjaman buku hanya dibatasi 3 buku, dan lama peminjaman hanya 10 hari jika lewat akan dikenai denda.

entitas dan atribut dari studi kasus di atas :
- Siswa: NIS, Nama, Kelas, JK
- Pegawai: NIP, Nama, Alamat, Jenis kelamin
- Petugas: NIP_petugas, Nama, Alamat, Jenis kelamin
- Buku : Kode_buku, ISBN, Judul, Pengarang, Penerbit, Jumlah Buku
- Peminjaman : Id_pinjam, Nis/Nip, Kode_buku, Tanggal, Nip_petugas
- Pengembalian : Id_pengembalian, Id_pinjam, keterlambatan

#### Relasi
contoh relasi :
Many to many: setiap entitas bisa mempunyai relasi dengan entitas lain, dan sebaliknya. Contoh: siswa dan ekstrakurikuler.
![relasi](https://dwblog-ecdf.kxcdn.com/wp-content/uploads/2019/08/simbol-relasi-many-to-many.png)

#### Membuat tabel dengan query
SQL atau Structured Query Language merupakan bahasa kueri yang paling populer dan sering digunakan. Bahasa pemrograman ini digunakan untuk mengakses, memanipulasi serta mengubah data yang berbasis relasional.Query ini sangat familiar dalam pengolahan database.

contoh cara membuat database dengan query :
```
create table siswa (
    nis int(5) not null,
    nama_siswa varchar(40),
    alamat_siswa varchar(50),
    tgl_lahir date,
    PRIMARY KEY(nis)
    );
```
dan hasilnya akan seperti di bawah ini :
![query](https://1.bp.blogspot.com/-Yhoqi1SbjVs/Xprc1zqa73I/AAAAAAAAA2c/ksqBivKZHTgkQBhMStJuJZZlFUOw9RYVQCLcBGAsYHQ/s1600/mysql2.png)



**Muhammad Rafi Kusdiarto**