# Writing Week 6, 24 - 28 Oktober 2022)

## Backend Development
---
Secara teknologi, Back-end adalah segala macam teknologi yang ada di sisi server dari sebuah website atau aplikasi. Back-end developers dapat memilih dari sekian banyak bahasa pemrograman dan framework, tetapi itu semua tergantung pada jenis aplikasi apa yang dibuat.
---
Bahasa yang digunakan pada Back End:
![web server](https://blogger.googleusercontent.com/img/a/AVvXsEj-uW73vDqVAccT47iZelHWRQ3sAO7j1BjHhnrIvfbmOSVpgSlDXh9IiJaiDnwmKTowGy6Wt_hfkIG8MIyD770HAWnS-PR8u6_AhbQrdIGZB8VxE-INCFNvndO3m2N7C8GYvv-ucmYQs3t-W-imELVBw6eltYKSNEI69v1PgR3JlQ8NpR075W2Hjh3BzQ=s600-rw)

### Database 
---
Database dapat didefinisikan sebagai kumpulan data yang disimpan secara sistematis di dalam komputer yang dapat diolah dan dimanipulasi. Database bisa juga disebut sebagai gudang penyimpanan data untuk diolah lebih lanjut.
---
Tools database :
![database](https://www.trickyenough.com/wp-content/uploads/2020/07/list-of-popular-databases-scaled.jpg)

- Database Management System
DBMS adalah software yang dapat digunakan oleh user untuk berkomunikasi dengan data yang ada dalam media penyimpanan.

Istilah pada database
- Table
- Field
- Record
#### SQL
SQL adalah Bahasa Query yang digunakan untuk melakukan interaksi di RDMS (Relational Database Management System) 

#### DDL (Data Definition Language)
DDL merupakan kumpulan perintah SQL yang digunakan untuk membuat, mengubah dan menghapus struktur dan definisi metadata dari objek-objek Database.

- ALTER : digunakan untuk mengubah struktur dari tabel yang ada, seperti untuk menambahkan atau menghapus kolom
- DROP : digunakan untuk menghapus Database, Table, dan View atau Index.

#### DML (Data Manipulation Language)
- SELECT : digunakan untuk menyeleksi data berdasarkan syarat yang diberikan.
- INSERT : igunakan untuk memasukkan data ke kolom-kolom yang terdapat pada tabel/view.
- Where, And, Or, Not, Like 
- UPDATE : digunakan untuk melakukan editing pada isi dari kolom (field) yang dipilih. Hal ini dilakukan untuk memperbaiki data lama / terjadi kesalahan.
- DELETE : menghapus data dalam tabel yang menjadi target.

#### DCL (Data Control Language)
- GRANT : digunakan untuk memberikan hak akses pada user.
- REVOKE : digunakan untuk mencabut hak akses yang telah diberikan pada user.

#### Database Relationships
database relationship adalah relasi atau hubungan antara beberapa tabel dihubungkan oleh Primary key dan foreign key.
- Contoh : NIM dalam tabel Mahasiswa, merupakan nilai yg Unik yang tidak mungkin bersifat ganda.

tipe relationship database :
- One To One Relationships
- One to Many and Many to One 
- Relationships
- Many to Many Relationships
- Self Referencing Relationships

#### NO SQL
database yang tidak memiliki perintah SQL. penyimpanannya semi struktural atau tidak struktural, dan tidak harus memiliki relasi layaknya tabel-tabel MySQL.

Kelebihan :
- NoSQL bisa menampung data yang terstruktur, semi terstruktur dan tidak terstruktur.
- Menggunakan OOP dalam pengaksesan/manipulasi data.
- NoSQL tidak mengenal schema tabel yang kaku.



### APIs: Application Programming Interfaces
---
API adalah sekumpulan instruksi program dan protokol yang digunakan untuk membangun aplikasi perangkat lunak.

REST API bertugas sebagai penghubung/perantara antara Front-End dan Back-end untuk saling bertukar informasi(request dan response).

### MERN Stack
MERN adalah salah satu kombinasi teknologi antara front-end dan back-end untuk membuat aplikasi website.
![mern](https://www.rlogical.com/wp-content/uploads/2020/12/MERN-Stack-considered-the-Best-for-Developing-Web-Apps.png)


## MySQL Lanjutan

### Relation pada Database
- Relasi One to One

Relasi One to One adalah relasi yang mana setiap satu baris data pada tabel pertama hanya berhubungan dengan satu baris pada tabel kedua 
contoh :

![relasa](https://aantamim.id/images/one-to-one-visual_hu0612e3d17f2e94a2e0dca53586185904_12012_750x0_resize_q100_h2_box_3.webp)

- Relasi One to Many

Relasi One to Many adalah relasi yang mana setiap satu baris data pada tabel pertama berhubungan dengan lebih dari satu baris pada tabel kedua
contoh :

![relasi](https://aantamim.id/images/one-to-many-visual_hub442cbc453a8cc4df7dd918b29008601_14186_750x0_resize_q100_h2_box_3.webp)

- Relasi Many to Many

Relasi Many to Many adalah relasi yang mana setiap lebih dari satu baris data dari tabel pertama berhubungan dengan lebih dari satu baris data pada tabel kedua. Artinya, kedua tabel masing-masing dapat mengakses banyak data dari tabel yang direlasikan.

contoh :

![](https://aantamim.id/images/many-to-many-visual_huc461f8750d17635a1e8c35a9dc694a6f_6480_526x0_resize_q100_h2_box_3.webp)

### Database Normalization
Teknik analisis data yang mengorganisasikan atribut-atribut data dengan cara mengelompokkan sehingga terbentuk entitas yang non-redundant, stabil, dan fleksible.

Tujuan Database Normalization
- Menghilangkan redundan data pada database.
- Memudahkan juka ada perubahan struktur table database.
- Memperkecil pengaruh jika ada perubahan dari struktur table database.


Jika data dalam database tersebut belum di normalisasi maka akan terjadi 3 kemungkinan yang akan merugikan sistem secara keseluruhan.

- INSERT Anomali : Situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
- DELETE Anomali: Penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
- UPDATE Anomali: Situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.

Tahapan Normalisasi Database
- Unnormalize

Bentuk tidak normal (unnormalized) merupakan kumpulan data yang direkam tidak ada keharusan dengan mengikuti suatu format tertentu.

Pada bentuk tidak normal terdapat repeating group (Pengulangan Group), sehingga pada kondisi ini data menjadi permasalahan dalam melakukan manipulasi data (insert, update, dan delete) atau biasa disebut anomali.

![](https://miro.medium.com/max/875/1*BH7g0xo1w1vnbleC83cjLw.png)

- 1NF / First Normal Form

1NF mensyaratkan beberapa kondisi dalam sebuah database, berikut adalah fungsi dari bentuk normal pertama ini.

- Menghilangkan duplikasi kolom dari tabel yang sama.
- Buat tabel terpisah untuk masing-masing kelompok data terkait dan mengidentifikasi setiap baris dengan kolom yang unik (primary key).

![](https://miro.medium.com/max/875/1*pxBZkOwTiOehvGIo1dRR-A.png)
Pada intinya bentuk normalisasi 1NF ini mengelompokkan beberapa tipe data atau kelompok data yang sejenis agar dapat dipisahkan sehingga anomali data dapat di atasi.

### Join Multiple Tables
---
Mengambil records dari dua atau lebih table database yang memiliki relationship dan akan di sajikan dalam single result set.

- INNER JOIN : Semua baris akan diambil dari kedua table yang akan di JOIN, selama columns cocok dengan kondisi yang sudah di tentukan.
```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```
- LEFT JOIN : Pada JOIN ini, semua records dari table di sisi kiri JOIN statement akan di pilih.
```
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```
- RIGHT JOIN : semua records dari table di sisi kiri JOIN statement akan di pilih, bahkan jika table di sebelah kiri tidak memiliki record yang cocok.
```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

### Aggregate Functions
---
Mengambil satu nilai setelah melakukan perhitungan pada sekumpulan nilai

- MIN : fungsi mengembalikan nilai terkecil dari kolom yang dipili
```
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```
- MAX : fungsi mengembalikan nilai terbesar dari kolom yang dipilih
```
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```
- SUM : fungsi mengembalikan jumlah total kolom numerik.
```
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```
- AVG : mengembalikan nilai rata-rata kolom numerik
```
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```
- COUNT : mengembalikan jumlah baris yang cocok dengan kriteria yang ditentukan.
```
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```
- UNION : Digunakan untuk menggabungkan kumpulan hasil dari dua atau lebih pernyataan SELECT.
```
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;
```
- GROUP BY : Mengelompokkan baris yang memiliki nilai yang sama ke dalam baris ringkasan
```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```
- HAVING : HAVING ditambahkan ke SQL karena kata kunci WHERE tidak dapat digunakan dengan aggregate functions.
```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```
- LIKE : digunakan dalam klausa WHERE untuk mencari pola tertentu dalam kolom.
```
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```


## Authentication & Authorization in Express JavaScript Authentication

### Pengertian Authentication
---
Authentication merupakan proses untuk memastikan suatu pengenalan atau memastikan suatu kebenaran

Proses authentication bisa meliputi

- Apa yang diketahui oleh hanya orang itu misalnya password
Seseorang yang login dengan suatu username dan password yang hanya dia yang tahu maka dapat dipastikan bahwa orang itu benar-benar login ke sistem

- Apa yang dimiliki oleh orang itu misalnya kartu akses atas nama dia
Pada suatu perusahaan mungkin dibuatkan suatu kartu akses yang dapat membuka pintu. Jika pintu terbuka maka log mengenai kartu tersebut akan terekam, dan pemiliknya akan disebut sebagai karyawan yang menbuka pintu tersebut

- Biometric misalnya sidik jari
Setiap karyawan yang yang datang ke kantor pagi hari akan melakukan presensi dengan sidik jari

Tipe authentication :
- Token Authentication
- Passwords 
- Behavior Biometrics
- Multi-Factor Authentication
- Single Sign-On 

### Pengertian Authorization
---
authorization adalah proses selanjutnya setelah authentication berhasil. Sistem akan memberikan akses sesuai kebijakan yang sudah ditentukan sebelumnya. Di sini sistem akan memberikan batasan akses yang akan diberikan kepada karyawan yang sudah login tersebut.

Tipe authentication : 
- hak akses untuk admin
- hak akses untuk user

### Perbedaan Authentication vs Authorization
Authentication :
- Memverfikasi siapa pengguna sebenarnya	
- Bekerja menggunakan kata sandi, OTP, informasi biometrik, dan informasi lain yang diberikan atau dimasukkan oleh pengguna.	
- Tahap pertama dalam proses pemeriksaan keamanan	
- Terlihat dan sebagian dapat diubah oleh pengguna	

Authorization :
- Menentukan sumber daya apa yang dapat diakses pengguna.
- Bekerja berdasarkan peraturan yang telah ditetapkan oleh developer atau organisasi pemilik aplikasi
- Selalu dijalankan setelah proses authentication selesai
- Tidak terlihat dan tidak dapat diubah oleh pengguna

### Penggunaan Authentication dan Authorization
Penggunaan disini tentang cara kerja JSON Web Token, apa kelebihannya, strukturnya, dan cara menggunakannya untuk menangani otentikasi dan otorisasi dasar di Express.

#### JWT 
JSON Web Token, yang berarti token ini menggunakan JSON (Javascript Object Notation) berbentuk string panjang yang sangat random, lalu token ini memungkinkan kita untuk mengirimkan data yang dapat diverifikasi oleh dua pihak atau lebih.

- cara kerja JWT 
![JWT](https://stackabuse.s3.amazonaws.com/media/authentication-and-authorization-in-expressjs-using-jwt-1.png)

Seperti password jadi ketika users berhasil melakukan Login maka server akan memberikan sebuah Token. Nanti Token tersebut akan disimpan oleh users pada Local Storage atau Cookies Browser dan bila users ingin mengakses halaman halaman tertentu maka harus menyertakan token tersebut.

#### Struktur JWT
- Header
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```
- Payload
```
{
  "sub": "1234567890",
  "name": "Minpo",
  "admin": true
}
```
- Verify Signature : adalah hasil dari Hash atau gabungan dari isi encode Header dan Payloadnya lalu ditambahkan kode secretnya.
```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

Dan hasil ketiga bagian tersebut akan digabung dan otomatis di encode menjadi Token string random panjang seperti berikut
![](https://i.ibb.co/xHKBcf5/jwt.png)

#### Cara penerapan di Express JS
- membuat projek kosong dan install express
```
npm init -y
```
```
npm install --save express
```
- mendeklarasikan data yang menyimpan data user
```
const users = [
    {
        username: 'john',
        password: 'password123admin',
        role: 'admin'
    }, {
        username: 'anna',
        password: 'password123member',
        role: 'member'
    }
];
```
- install modul JWT nya dan memanggilnya
```
npm i --save body-parser jsonwebtoken
```
```
const jwt = require('jsonwebtoken');
const bodyParser = require('body-parser');

app.use(bodyParser.json());
```
- membuat variabel untuk menampung token
```
const accessTokenSecret = 'youraccesstokensecret';
```
- lalu menggunakan string acak untuk token dan digunakan pada saat login
```
app.post('/login', (req, res) => {
    // Read username and password from request body
    const { username, password } = req.body;

    // Filter user from the users array by username and password
    const user = users.find(u => { return u.username === username && u.password === password });

    if (user) {
        // Generate an access token
        const accessToken = jwt.sign({ username: user.username,  role: user.role }, accessTokenSecret);

        res.json({
            accessToken
        });
    } else {
        res.send('Username or password incorrect');
    }
});
```

- lalu kita coba run
```
node index.js
```

- lalu akan diarahkan ke http://localhost:3000/login, dan akan muncul 
![](https://stackabuse.s3.amazonaws.com/media/authentication-and-authorization-in-expressjs-using-jwt-5.png)
```
{
    "username": "john",
    "password": "password123admin"
}
```
```
  "accessToken": "eyJhbGciOiJIUz..."
```

## Sequelize
----
Sequelize adalah ORM (Object Relational Mapping) Node JS yang berbasis promise. Sequelize mendukung sebagian besar relational Database seperti MySQL, PostgresQL, MariaDB, SQLite dan Miscrosoft SQL Server.

Dengan fitur fitur di Sequelize, kita bisa mengelola dan mengatur data di database kita dengan cepat, dan efisien.

### Instalasi Sequelize 
- buka terminal pada project kita dan ketikkan 
```
npm install --save-dev sequelize-cli
```
- install driver database
```
npm install mysql2
```
- membuat folde sequelize
```
npx sequelize init
```
- setting database 
```
import {Sequelize} from "sequelize";

const db = new Sequelize('mylist', 'root', '',{
    host: 'localhost',
    dialect: 'mysql'
});

export default db;
```
- generate model dengan mengetikkan 
```
npx sequelize-cli model:generate --name Mhs --attributes nama:string, nim:string
```
- membuat database dari sequelize
```
npx sequelize-cli db:migrate
```
- generate seed dan dijalankan
```
npx sequelize-cli seed:generate --name data-mhs
```
```
npx sequelize-cli db:seed:all
```

#### Membuat CRUD
- get all todo item
```
import ListTodo from "../models/ItemsModel.js";

export const getListTodo = async(req, res) => {
    try {
        const response = await ListTodo.findAll();
        res.status(200).json(response);
        console.log("succes akses ke tabel")
    } catch (error) {
        console.log(error.message);
    }
}
```

- menampilkan item todo by id
```
export const getListTodoByID = async(req, res) => {
    try {
        const response = await ListTodo.findOne({
            where:{
                id: req.params.id
            }
        });
        res.status(200).json(response)
        console.log("succes dapatkan id")
    } catch (error) {
        console.log(error.message)
    }
}
```

- menambakan item todo
```
export const createTodoList = async(req, res) => {
    try {
        await ListTodo.create(req.body);
        res.status(201).json({message:"menambahkan Item"});
    } catch (error) {
        console.log(error.message)
    }
}
```

- edit item todo
```
export const updateTodoList = async(req, res) => {
    try {
        await ListTodo.update(req.body,{
            where:{
                id:req.params.id
            }
        });
        res.status(200).json({message:" Item updated"});
    } catch (error) {
        console.log(error.message)
    }
}
```

- hapus item todo
```
export const deleteTodoList = async(req, res) => {
    try {
        await ListTodo.destroy({
            where:{
                id:req.params.id
            }
        });
        res.status(200).json({message:" Item deleted"});
    } catch (error) {
        console.log(error.message)
    }
}
```

#### Membuat RESTFul API
- menampilkan semua item todo
```
GET http://localhost:5000/list-todo
```

- menampilkan todo dengan id tertentu
```
GET http://localhost:5000/list-todo/1
```

- menambahkan todo baru
```
POST http://localhost:5000/list-todo
```

- update/edit todo
```
PATCH  http://localhost:5000/list-todo/5
```

- hapus todo
```
DELETE  http://localhost:5000/list-todo/4
```


***Muhammad Rafi Kusdiarto**