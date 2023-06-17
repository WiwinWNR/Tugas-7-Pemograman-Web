# Praktikum 10: Pagination dan pencarian
# Langkah-Langkah Praktikum
# Membuat Pagination
Pagination merupakan proses yang digunakan untuk membatasi tampilan yang panjang 
dari data yang banyak pada sebuah website. Fungsi pagination adalah memecah tampilan 
menjadi beberapa halaman tergantung banyaknya data yang akan ditampilkan pada 
setiap halaman.
Pada Codeigniter 4, fungsi pagination sudah tersedia pada Library sehingga cukup mudah 
menggunakannya.
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi kode 
pada method admin_index seperti berikut. 
![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/27005655-32ff-4aa0-8f0e-ac66ab0b9236)

Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut dibawah deklarasi tabel data.
 <?= $pager->links(); ?>

Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat hasilnya.

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/b89d4fff-9025-4e1f-b643-e981349e898e)

# Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali Controller Artikel, pada method admin_index ubah kodenya seperti berikut

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/5975a4b4-45e1-4907-9a53-f79b9400b9df)

Kemudian buka kembali file views/artikel/admin_index.php dan tambahkan form 
pencarian sebelum deklarasi tabel seperti berikut:

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/3d4531fc-11b0-460b-9123-a8dcc259f1c7)

Dan pada link pager ubah seperti berikut.

<?= $pager->only(['q'])->links(); ?>

Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata kunci tertentu pada form pencarian.

![image](https://github.com/WiwinWNR/Tugas-7-Pemograman-Web/assets/115921167/1fbe4824-4105-42fb-8310-258aa6641fb0)



