# TUGAS 7 PEMOGRAMAN WEB
# Langkah-Langkah Praktikum
1. Mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/dc739981-e62a-42c4-b4ee-a60da4b33d4a)

2. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/8905655b-fd2a-445d-9ff1-3a2cb2f0ab55)

3. Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual. http://localhost/lab7_php_ci/ci4/public/

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/0bc63159-198c-479b-8af9-b6563c756433)

4. Menjalankan CLI (Command Line Interface)
Menjalankan CLI (Command Line Interface) Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.

![Screenshot (167)jkj](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/d0b1403b-1292-4f55-9ce8-9846077fae51)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab11_ci/ci4/)
* PHP SPARK

![Screenshot (168)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/05646fec-edfb-4b25-b61b-cb9aa21fdd72)

5. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

![F](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/71980c2a-8b6f-47ca-8f5f-453afb945811)

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRONMENT menjadi development.

![Screenshot (176)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/e3183b48-bbf1-4e20-8ccb-9adf6a5a5814)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable CI_ENVIRONMENT menjadi development.

![Screenshot (172)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/805fd5d6-0ce0-45b2-b91c-a9bf613233a7)

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file app/Controller/Home.php hilangkan titik koma pada akhir kode.

![Screenshot (171)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/9ba82603-fb4a-4679-92d6-fc1d65ff1d76)

6. Membuat Routes Baru
Tambahkan code pada routes.php

* $routes->get('/about', 'Page::about');
* $routes->get('/contact', 'Page::contact');
* $routes->get('/faqs', 'Page::faqs');

![Screenshot (173)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/28e5d1f2-baca-46a0-b0f6-a7cc315603df)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.

* PHP Spark Routes

![T](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/179e09fb-7cf4-40ea-a0a9-efa8abf74196)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about

![FH](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/50d1a2dc-d8ad-400d-9744-16b482d46dec)

7. Membuat Controller

Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.

![Screenshot (178)H](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/fa3fdd4c-27fe-4f4f-964a-36824f55d89d)


Berikut hasil nya

![172894574-5c23e907-b3e6-4974-a08a-869b5c81d08aL](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/5cd0d949-7f55-46c0-9bbf-91c8196b5f44)

8. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

* $routes->setAutoRoute(true);

Tambahkan method baru pada Controller Page seperti berikut.

![Screenshot (179)F](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/0375c80b-c02e-4c0b-969b-d117bad954da)

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos

![172894988-bf9189f6-e9c6-4b6b-ac02-bb565e801108F](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/e9955780-d677-4f4d-9757-e4f860aa8b4e)

9. Membuat View
Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.
![Screenshot (180)K](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/d0c6741e-d0bc-457e-a320-14717d651a14)

Ubah method about pada class Controller Page menjadi seperti berikut:
![Screenshot (180)F](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/8f134de0-4be6-42a9-923e-86b320d21f6b)
    
Lalu refresh halaman tersebut

![172895350-5877486d-b30a-4515-9f4e-bcff4700c208;](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/a9bca371-3073-4ca3-be32-89dfc63dbcac)

10. Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![Screenshot (177)](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/5473015f-ec5c-4c35-b5cf-a79010acd614)

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

![172895934-a5c34709-043f-4024-953a-c7e04bbea443K](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/08602056-fb97-4990-ad45-99d75338a906)

