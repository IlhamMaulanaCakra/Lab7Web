# Lab7Web

<h3>Biodata Mahasiswa</h3>           
    <table>
        <p><tr>
               <td>Kelas</td>
               <td>:</td>
               <td>TI.21.A.1</td>
               <td>&nbsp;</td>
       </tr></p>
       <p><tr>
               <td>Nama</td>
               <td>:</td>
               <td>Ilham Maulana Cakra Dwi Noto</td>
               <td>&nbsp;</td>
       </tr></p>
       <p><tr>
               <td>Nim</td>
               <td>:</td>
               <td>312110027</td>
               <td>&nbsp;</td>
       </tr></p>
       </table>

<h3>Tujuan</h3>

1. Mahasiswa mampu memahami konsep dasar Framework.
2. Mahasiswa mampu memahami konsep dasar MVC.
3. Mahasaswa mampu membuat program sederhana menggunakan Framework Codeigniter4.
Instruksi Praktikum
1. Persiapkan text editor misalnya VSCode.
2. Buat folder baru dengan nama lab11_php_ci pada docroot webserver (htdocs)
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

<h3>Langkah-langkah Praktikum
Persiapan</h3>

Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver.
Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:
1. php-json ekstension untuk bekerja dengan JSON;
2. php-mysqlnd native driver untuk MySQL;
3. php-xml ekstension untuk bekerja dengan XML;
4. php-intl ekstensi untuk membuat aplikasi multibahasa;
5. libcurl (opsional), jika ingin pakai Curl.

<h3>Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config
-> PHP.ini</h3>

![Screenshot (29)](https://user-images.githubusercontent.com/92771347/236993057-4b7961de-5023-4d3f-8857-a5c27dd30c7f.png)

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian
simpan kembali filenya dan restart Apache web server.

![Screenshot (30)](https://user-images.githubusercontent.com/92771347/236994257-5cd38f53-366c-4cc7-a0c3-3ea38e250f69.png)

<h3>Membuat Layout Web dengan CSS</h3>

<h3>Instalasi Codeigniter 4</h3>

Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan
menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
1. Unduh Codeigniter dari website https://codeigniter.com/download
2. Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
3. Ubah nama direktory framework-4.x.xx menjadi ci4.
4. Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

![Screenshot (31)](https://user-images.githubusercontent.com/92771347/236995283-1e6d1809-9d45-4a77-a2f4-d8c2b0728669.png)

<h3>Menjalankan CLI (Command Line Interface)</h3>

Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka
terminal/command prompt. 
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab11_ci/ci4/)
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:

```php spark```

![Screenshot (32)](https://user-images.githubusercontent.com/92771347/236996217-483a27dd-6fa1-4e85-9591-a16d487529ec.png)

<h3>Mengaktifkan Mode Debugging</h3>

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan
error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif.
Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu
diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable
CI_ENVIRONMENT menjadi development. Ubah nama file env menjadi .env kemudian buka file tersebut.

![Screenshot (33)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/454f2cf7-6bba-432f-afd3-15dcc7677f0a)

<h3>Struktur Direktori</h3>

Untuk lebih memahami Framework Codeigniter 4 perlu mengetahui struktur direktori dan file yang
ada. Buka pada Windows Explorer atau dari Visual Studio Code -> Open Folder.
Terdapat beberapa direktori dan file yang perlu dipahami fungsi dan kegunaannya.
1. github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk
build dengan github action;
2. app folder ini akan berisi kode dari aplikasi yang kita kembangkan;
3. public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php, robots.txt,
favicon.ico, ads.txt, dll;
4. tests folder ini berisi kode untuk melakukan testing dengna PHPunit;
5. vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk kode
core dari system CI.
6. writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk
menyimpan file yang di-upload, logs, session, dll.
Sedangkan file-file yang berada pada root direktori CI sebagai berikut.
7. .env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.
8. .gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git.
9. build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi release
(stabil) dan development (labil).
10. composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar library
yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.
11. composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan aplikasi.
12. license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter;
13. phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit.
14. README.md adalah file keterangan tentang codebase CI. Ini biasanya akan dibutuhkan
pada repo github atau gitlab.
15. spark adalah program atau script yang berfungsi untuk menjalankan server, generate kode,
dll.

![Screenshot (34)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/c2713d90-0471-4cc5-a706-993f812f8904)

Fokus kita pada folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi.
Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.

<h3>Memahami Konsep MVC</h3>

Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari Model-View-Controller. MVC
merupakan konsep arsitektur yang umum digunakan dalam pengembangan aplikasi. Konsep MVC
adalah memisahkan kode program berdasarkan logic proses, data, dan tampilan. Untuk logic proses
diletakkan pada direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan
diletakkan pada direktori View.

Codeigniter menggunakan konsep pemrograman berorientasi objek dalam mengimplementasikan
konsep MVC.

<b>Model</b> merupakan kode program yang berisi pemodelan data. Data dapat berupa database ataupun
sumber lainnya.

<b>View</b> merupakan kode program yang berisi bagian yang menangani terkait tampilan user interface
sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan dengan html dan css.

<b>Controller</b> merupakan kode program yang berkaitan dengan logic proses yang menghubungkan
antara view dan model. Controller berfungsi untuk menerima request dan data dari user kemudian
diproses dengan menghubungkan bagian model dan view.

<h3>Routing dan Controller</h3>

Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan
fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, routing bertujuan
untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau
script yang bertanggung jawab merespon sebuah request.

Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian
oleh router tesebut diarahkan ke Controller.

Router terletak pada file app/config/Routes.php

![Screenshot (35)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/a6141526-7b54-4d63-851b-b84b0c7ccefd)

Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Contoh:

```$routes->get('/', 'Home::index');```

Kode tersebut akan mengarahkan rute untuk halaman home.

<b>Membuat Route Baru.</b>

Tambahkan kode berikut di dalam Routes.php

`$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');`

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.

```php spark routes```

![Screenshot (36)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/e15b17b7-f13a-4170-9eb4-f7e25f41b039)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![Screenshot (37)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/6d745b4a-2e3a-46b2-82d4-4c871ebc3c02)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada.
Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan
routing yang dibuat yaitu Contoller Page.

<b>Membuat Controller</b>

Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori
Controller kemudian isi kodenya seperti berikut.

```
<?php
namespace App\Controllers;

class Page extends BaseController
{
    public function about()
    {
        echo "Ini halaman About";
    }
    public function contact()
    {
        echo "Ini halaman Contact";
    }
    public function faqs()
    {
        echo "Ini halaman FAQ";
}
}
```

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah dapat
diakses.

![Screenshot (38)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/ba354732-3aeb-4698-a3c8-b58e9e1b28b0)

<b>Auto Routing</b>

Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat
mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

```
$routes->setAutoRoute(true);

Tambahkan method baru pada Controller Page seperti berikut.

public function tos()
{
    echo "ini halaman Term of Services";
}
```

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat:
http://localhost:8080/page/tos

![Screenshot (39)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/c716a199-fa6a-4b10-8692-5e0af32233f5)

<h3>Membuat View</h3>

Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan
nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title><?= $title; ?></title>
</head>
<body>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
</body>
</html>
```

Ubah method about pada class Controller Page menjadi seperti berikut:
```
public function about()
{
    return view('about', [
        'title' => 'Halaman Abot',
        'content' => 'Ini adalah halaman abaut yang menjelaskan tentang isi
halaman ini.'
    ]);
}
```

Kemudian lakukan refresh pada halaman tersebut.

![Screenshot (40)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/d40041f2-0696-4f0a-8d68-569b78299dfe)

<h3>Membuat Layout Web dengan CSS</h3>

Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang
perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada
direktori public.
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita
akan gunakan layout yang pernah dibuat pada praktikum 4.

![Screenshot (41)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/8abf9e6b-a5dc-4716-9362-85c3f7078416)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php
File app/view/template/header.php

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title><?= $title; ?></title>
    <link rel="stylesheet" href="<?= base_url('/style.css');?>">
</head>
<body>
    <div id="container">
    <header>
        <h1>Layout Sederhana</h1>
    </header>
    <nav>
        <a href="<?= base_url('/');?>" class="active">Home</a>
        <a href="<?= base_url('/artikel');?>">Artikel</a>
        <a href="<?= base_url('/about');?>">About</a>
        <a href="<?= base_url('/contact');?>">Kontak</a>
    </nav>
    <section id="wrapper">
        <section id="main">
```

File app/view/template/footer.php
```
</section>
        <aside id="sidebar">
            <div class="widget-box">
                <h3 class="title">Widget Header</h3>
                <ul>
                    <li><a href="#">Widget Link</a></li>
                    <li><a href="#">Widget Link</a></li>
                </ul>
            </div>
            <div class="widget-box">
                <h3 class="title">Widget Text</h3>
                <p>Vestibulum lorem elit, iaculis in nisl volutpat,
                malesuada tincidunt arcu. Proin in leo fringilla, vestibulum mi porta,
                faucibus felis. Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
            </div>
        </aside>
    </section>
    <footer>
    <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
    </div>
</body>
</html>
```

Kemudian ubah file app/view/about.php seperti berikut.

```
<?= $this->include('template/header'); ?>
<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>
<?= $this->include('template/footer'); ?>
```
Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![Screenshot (42)](https://github.com/IlhamMaulanaCakra/Lab7Web/assets/92771347/63899e50-e04c-4cca-94fd-9a38b6cb7a4a)



