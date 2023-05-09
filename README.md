# Lab4Web

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
CI_ENVIRINMENT menjadi development.


