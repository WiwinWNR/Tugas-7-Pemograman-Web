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

public function admin_index() 
 {
 $title = 'Daftar Artikel';
 $model = new ArtikelModel();
 $data = [
 'title' => $title,
 'artikel' => $model->paginate(10), #data dibatasi 10 record 
per halaman
 'pager' => $model->pager,
 ];
 return view('artikel/admin_index', $data);
 }
