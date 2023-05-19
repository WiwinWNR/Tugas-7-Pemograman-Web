# Tugas-7-Pemograman-Web
Langkah - langkah Praktikum
1. Mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/31607a6a-a174-4e45-9950-2eacbafe72d4)
2. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/7f42900f-5bc1-40ff-b419-ae6ddde73b4d)
3. Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual. http://localhost/lab7_php_ci/ci4/public/
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/34b5637c-5b70-43d1-97ae-b479833e5ef4)
4. Menjalankan CLI (Command Line Interface)
Menjalankan CLI (Command Line Interface) Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/3b4fc1f6-8704-4435-ba17-23a46ba3817d)
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab7_php_ci/ci4/)
PHP Spark
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/f9eaf556-fbca-4ef3-8f2a-a2c809b8d90a)
5. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/2374c62e-b6e7-4c92-b069-6da6c60f4c49)
Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRONMENT menjadi development.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/0115cddb-6763-4fd7-a6c4-0ec005f1b7dd)
Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable CI_ENVIRONMENT menjadi development.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/8d80b3cf-c5f1-4176-8d7c-cfbe6d5c7cf3)
Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file app/Controller/Home.php hilangkan titik koma pada akhir kode.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/c2fdb432-56e6-4def-8cf2-f8908550c005)
6. Membuat Routes Baru
Tambahkan code pada routes.php

$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/e0339aca-bd20-404e-baa0-f3ca90a36585)
Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.

PHP Spark Routes
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/b8ade825-28e9-4020-9ac6-754da958d78b)
Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/6ed85380-6d6c-49ad-8879-ec2b4cd87f93)
Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

7. Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.
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
Berikut hasil nya
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/8581ba29-c055-41b9-b114-eac3c54de5ae)
8. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

$routes->setAutoRoute(true);
Tambahkan method baru pada Controller Page seperti berikut.

  public function tos()
    {
        echo "ini halaman Term of Services";
    }
Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/6665ea2e-4ba0-4a8d-9ba9-9e0d55386acd)
9. Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.

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
Ubah method about pada class Controller Page menjadi seperti berikut:

public function about()
    {
        return view('about', [
            'title' => 'Halaman About',
            'content' => 'Ini adalah halaman about yang menjelaskan tentang isi halaman ini.'
        ]);
    }
Lalu refresh halaman tersebut
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/5ff96271-0fcf-4251-8c08-ab54e5759f27)
10. Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/2d2b4473-98d8-4de3-a7a0-56ae3c623be4)
Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php

File app/views/template/header.php
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
File app/views/template/footer.php
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
            <p>Vestibulum lorem elit, iaculis in nisl volutpat, malesuada
tincidunt arcu. Proin in leo fringilla, vestibulum mi porta, faucibus felis.
Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
        </div>
    </aside>
</section>
<footer>
    <p>&copy; 2022 - Universitas Pelita Bangsa</p>
</footer>
</div>
</body>
</html>
Kemudian ubah file app/view/about.php seperti berikut.
<?= $this->include('template/header'); ?>

<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>

<?= $this->include('template/footer'); ?>
Lalu refresh halaman tersebut
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/6f30cfec-b6fa-4900-a28c-1e1d8e98f1e8)

