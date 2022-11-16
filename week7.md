# Writing Week 7, 7 - 10 November 2022)

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

## MongoDB & Mongoose
---
MongoDB adalah salah satu database open source NoSQL yang cukup populer digunakan.
Jika SQL menyimpan data menggunakan relasi tabel, MongoDB menggunakan dokumen dengan format JSON
- NoSQL

Database NoSQL adalah database non-relasional. Artinya data disimpan dalam kumpulan dokumen. Tidak ada struktur khusus untuk dokumen-dokumen ini, dan mereka tidak terhubung satu sama lain melalui hubungan. Jadi, mereka lebih cocok untuk menyimpan data yang tidak perlu diakses dengan cara tertentu.
- SQL

 Database SQL menggunakan pendekatan penskalaan vertikal, artinya mereka menskalakan dengan menambahkan lebih banyak daya ke server. Basis data NoSQL menggunakan pendekatan penskalaan horizontal, artinya mereka menskalakan dengan menambahkan lebih banyak server.


#### Kelebihan MongoDB dengan NoSQL
- Sistem tidak membutuhkan Tabel
- Tidak perlu menggunakan Tabel yang terstruktur
- By Default sudah menggunakan JSON(JavaScript Object Notation), sehingga memudahkan integrasi dengan JavaScript
- Performa lebih cepat dengan kemampuan menampung banyak data yang bervariasi

#### Kekurangan MongoDB dengan NoSQL
- Tidak mendukung transaksi
- Masalah konsistensi data
- Menggunakan banyak memory
- Hanya bisa menampung maksimal 16MB disetiap document

### Penggunaan pada expressJS
---
module yang digunakan :
- express : ```npm install express```
- mongoose :  ```npm install mongoose```
- dotenv : ```npm install dotenv```

Untuk mengakses database MongoDB dari express , harus menggunakan Mongoose yang merupakan Object Data Modelling library yang menyediakan semua fungsi yang diperlukan untuk mengakses dan bekerja dengan MongoDB.
di bawah ini langkah-langkah nya :
- Inisialisasi file utama express untuk ke server
```
const express = require("express");
const app = express();
app.listen(3000, () => console.log("Server is running"));
```
- menambahkan package dari mongoose
```
const mongoose = require("mongoose");
const app = express();
app.listen(3000, () => console.log("Server is running"));
```

- menyambungkan ke mongoDB server
```
mongoose.connect( 
    process.env.MONGODB_URL, 
    { 
        useNewUrlParser: true, 
        useUnifiedTopology: true 
    } 
);
```
- menambahkan ```dotenv``` di file utama
```
require("dotenv").config(); 
```

- mengetikkan url MongoDb pada dotenv untuk diakses pada file utama
```
MONGODB_URL="your-mongodb-uri-here"
```

- membuat schema untuk menyimpan data
```
const studentSchema = new mongoose.Schema({
    roll_no: Number,
    name: String,
    year: Number,
    subjects: [String]
});
```

- define model dengan mengirimkan schema dan nama untuk model.
```
const Student = mongoose.model('Student', studentSchema);
```

- menambahkan data pada schema
```
const stud = new Student({
    roll_no: 1001,
    name: 'Madison Hyde',
    year: 3,
    subjects: ['DBMS', 'OS', 'Graph Theory', 'Internet Programming']
});
stud
    .save()
    .then(
        () => console.log("One entry added"), 
        (err) => console.log(err)
    );
```

- memanggil data dengan API
```
app.get('/', (req, res) => {
    Student.find({}, (err, found) => {
        if (!err) {
            res.send(found);
        }
        console.log(err);
        res.send("Some error occured!")
    }).catch(err => console.log("Error occured, " + err));
});
```

- hasilnya akan seperti di bawah ini

![mongo](https://miro.medium.com/max/1100/1*tkjJm3tcahpD1D_6hlerdw.png)



## Docker
---
Docker men-sharing kernel dari host OS, serta meng-container-kan suatu aplikasi agar dapat dijalankan dimana saja dan kapan saja. Docker berfungsi sebagai penyedia layanan virtual bagi aplikasi yg diinstall pada sebuah host. 

Docker akan menyediakan hal-hal yang diperlukan untuk aplikasi mulai dari akses file, koneksi internet, hingga port agar aplikasi dapat berjalan dengan mulus

- Docker File : Blueprint untuk membuat image
- Image : Template untuk menjalankan container
- Container : Perwujudan dari image
- Docker Registry : Tempat untuk upload/download image

### Fungsi docker
- Mempermudah Pengembangan Aplikasi
- Menyederhanakan Konfigurasi
- Memudahkan Pengembangan Kode Pipeline
- Bisa Digunakan untuk Debugging
- Mendukung Multitenancy
- Meningkatkan Sumber Daya dengan Cepat

### Perintah Dasar Docker
- Mencari Image di Repository Docker
```
docker search <nama image>
```
- Mendownload Image
```
docker pull <nama image>
```
- Melihat Daftar Image yang telah di Download
```
docker images
```
- Menjalankan Image
```
docker run -it ubuntu
```
- Melihat Container yang Berjalan
```
docker ps
```
- Menghapus Image
```
docker rmi <ID Image>
```
- Menghapus Container
```
docker rm <ID Container>
```
- Membuat Container
```
docker container create --name ubuntu-test -i -t ubuntu /bin/bash
```
- Menjalankan Container
```
docker start <ID>
```
- Masuk ke Container
```
docker exec -it <ID Container> /bin/bash
```
- Mematikan Container
```
docker stop <ID>
```
---

**Muhammad Rafi Kusdiarto**