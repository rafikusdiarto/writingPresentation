# Writing Presentation Week 1

## Unix Command Line

## Git dan GitHub
- Git
> Git adalah sebuah tools/software bagi para programmer dan developer yang berfungsi sebagai control system untuk menjalankan proyek dalam pengembangan software. Tujuan penggunaan Git yaitu untuk mengelola source code program dengan menentukan baris serta kode yang akan ditambahkan atau diganti. 
- GitHub 
> GitHub adalah paltform untuk menyimpan source code untuk suatu proyek dan berkolaborasi dengan developer atau programmer lainnya. Di GitHub bisa melacak riwayat semua perubahan kode. Dengan begitu memungkinkan developer untuk berkolaborasi dalam pengerjaan proyek secara lebih efektif. GitHub menyediakan sebuah penyimpanan online bernama *repository*.
- Penggunaan Git dan GitHub
> membuat repo baru
```
git init cobaWeb
```
> menambahkan file baru
```
touch file.txt
```
> melakukan commit pada github
```
git commit -m "progress1.0"
```
> membuat terhubung ke remote repository
```
git remote add cobaWeb https://github.com/rafikusdiarto/cobaWeb.git
```
> melakukan push perubahan ke branch main
```
git push origin main
```
> lalu akan tampil seperti di bawah ini
![image](https://user-images.githubusercontent.com/90013398/192434436-eb282cf9-acca-471d-9710-bddcf3b4c263.png)

> melakukan clone, nanti repository yang sudah diclone akan masuk sesuai direktori pada git bash
![image](https://user-images.githubusercontent.com/90013398/192685395-891c431a-bfc1-46dc-bf6f-b9bd467ef44d.png)



## HTML
HTML adalah singkatan dari Hyper Text Markup Language yang digunakan untuk pembuatan kerangka sebuah website dan menampilkan konten-konten yang ada di dalam website.
- Kerangka HTML

![image](https://user-images.githubusercontent.com/90013398/192435724-20aeac2d-195e-4251-9fbe-4e1b694570af.png)
> kerangka di atas adalah kerangka awal yang akan muncul otomatis di vscode ketika kita mengetikkan *!* lalu *enter* dan merupakan kerangka dasar sebuah website. Ada beberapa tag yang juga akan muncul otomatis dan ketika dibuka di website akan seperti ini 

![image](https://user-images.githubusercontent.com/90013398/192436155-6c85a248-2656-40a9-a883-01c404e53c74.png)
- Beberapa Contoh Tag HTML
> tag untuk menampilan judul website

![image](https://user-images.githubusercontent.com/90013398/192436610-5aafc835-2143-46bd-9acd-d953fa5f2ca2.png)

> untuk menampung content

![image](https://user-images.githubusercontent.com/90013398/192437385-dc2226ca-4a0a-49c7-bac0-b3e47e785fe1.png)

> tag yang digunakan sebagai wadah untuk elemen HTML

![image](https://user-images.githubusercontent.com/90013398/192436757-cd92c62d-5734-4e34-9925-0a8215ad068c.png)

> tag yang digunakan untuk mendefinisikan heading HTML

![image](https://user-images.githubusercontent.com/90013398/192436965-57f8de40-33f8-4715-89cb-a0b1faa15ad4.png)

> tag untuk menampilkan paragraf

![image](https://user-images.githubusercontent.com/90013398/192440202-2574d219-658a-483c-a29e-1f9fe3d6a245.png)

> tag untuk menampilkan gambar dan video

![image](https://user-images.githubusercontent.com/90013398/192438036-3b5e29a4-b63f-4f2c-a081-45f354c5c2e4.png)

> lalu tampilan website akan seperti ini

![image](https://user-images.githubusercontent.com/90013398/192438804-b571c280-53f1-4566-87a8-035d2556f6b9.png)

> untuk deploy saya menggunakan vercel dan saya connect kan ke repository github saya

![image](https://user-images.githubusercontent.com/90013398/192685806-50563328-f881-4599-90d8-ee1655513f8a.png)

![image](https://user-images.githubusercontent.com/90013398/192685832-7ac2cbf0-1ed7-4c1f-b9b7-8901b390e5a3.png)

![image](https://user-images.githubusercontent.com/90013398/192685701-8f32dd5e-643a-4a27-8611-e71582d3ac7d.png)

> hasilnya url akan bisa diakses publik dan bisa diubah sesuai yang kita inginkan

![image](https://user-images.githubusercontent.com/90013398/192685958-26b99268-13c4-4e6b-a507-1a230862c39e.png)


## CSS
Cascading Style Sheet merupakan bahas komputer untuk mengatur beberapa komponen dalam sebuah web. seperti contoh untuk mengubah font, warna, ukuran, spasi konten, pembagian kolom, atau menambahkan animasi dan fitur lainnya.
- Penggunaan CSS
> **Inline CSS**
element *style* dimasukkan di dalam tag HTML seperti di bawah ini

![image](https://user-images.githubusercontent.com/90013398/192441323-fd46823f-5509-4559-8e32-f2a545c86ac1.png)

![image](https://user-images.githubusercontent.com/90013398/192443782-1ddd0364-7273-4d8f-acd8-d3d2490cc28d.png)


> **Internal CSS**
tag ```<style>``` ada di dalam tag ```<head>``` dan masih berada di file HTML

![image](https://user-images.githubusercontent.com/90013398/192442992-a8d836ad-9643-4a0d-a58c-79543fd0a01c.png)

> **External CSS**
membuat file baru dengan nama ```style.css``` dan mengaksesnya di tag ```<head>```

![image](https://user-images.githubusercontent.com/90013398/192443638-0ac480ba-3563-445c-8f2f-1b4bc79de1c2.png)

![image](https://user-images.githubusercontent.com/90013398/192443664-84b0282c-a893-47b0-a563-94e8a4aa8dd7.png)

![image](https://user-images.githubusercontent.com/90013398/192444014-21112ad1-6e84-4012-a82d-937980c7900b.png)

> **Selector CSS**
selector pada CSS adalah syntax yang digunakan untuk memilih elemen yang ingin diberi style
 untuk semua element ```*```
 untuk class menggunakan ```.class```
 untuk id menggunakan ```#id```
 untuk element , *contoh* ```p```
> CSS terdiri dari 3 syntax yaitu selector, property, dan value

![image](https://user-images.githubusercontent.com/90013398/192445710-637b9b51-2bcd-4d8d-bc19-b6ce97b90bff.png)
 
```h1``` : selector untuk elemen yang akan diubah stylenya yaitu h1
```color``` : property color untuk merubah warna h1
```blue``` : value untuk mendefinisikan warna yang diinginkan
> penggunaan flexbox yaitu untuk mengatur layout dari beberapa konten pada HTML

![image](https://user-images.githubusercontent.com/90013398/192692039-8b8ebf56-1d20-4aa4-b78a-c20da6773bd1.png)

 hasilnya seperti di bawah ini
 
 ![image](https://user-images.githubusercontent.com/90013398/192691883-602f5d65-1b03-4bc3-b29f-a74319fe12a0.png)

 
## Algortima

## Javascript


