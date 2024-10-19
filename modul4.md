<h1 align="center">LAPORAN PRAKTIKUM</h1>
<h2 align="center">ALGORITMA DAN PEMROGRAMAN 2</h2>

<h3 align="center">MODUL 4</h3>
<h4 align="center">PROSEDUR</h4>

<p align="center">
  <img src="telkomuniv.png" alt="Logo Telkom University" width="200">
</p>
<p align="center">
    <strong>Disusun Oleh:</strong><br>
    Meutya Azzahra Efendi / 2311102166<br>
</p>

<p align="center">
    <strong>Dosen Pengampu:</strong><br>
    Abednego Dwi Septiadi
</p>

<p align="center">
    PROGRAM STUDI S1 TEKNIK INFORMATIKA<br>
    FAKULTAS INFORMATIKA<br>
    TELKOM UNIVERSITY PURWOKERTO<br>
    2024
</p>


### I. DASAR TEORI

### 4.1 Definisi Procedure
Prosedur dapat dianggap sebagai potongan beberapa instruksi program menjadi suatu instruksi baru yang dibuat untuk mengurangi kerumitan dari kode progra, yang kompleks pada suatu program yang besar. Prosedur akan menghasilkan suatu akibat atau efek langsung pada program ketika dipanggil pada program utama. Suatu subprogram dikatakan prosedur apabila:
1. Tidak ada deklarasi tipe nilai yang dikembalikan, dan
2. Tidak terdapat kata kunci return dalam badan subprogram
Kedudukannya prsedur sama seperti instruksi dasar yang sudah ada sebelumnya (assignment) dan/atau instruksi yang berasal dari paket (fmt), seperti fmt.Scan dan fmt.Print. Karena itu selalu pilih nama prosedur yang berbentuk kata kerja atau sesuatu yang merepresentasikan proses sebagai nama dari prosedur. COntoh: cetak, hitunngRerata, cariNilai, belok, mulai, ...

### 4.2 Deklarasi Procedure
Berikut ini adalah cara penulisan deklarasi prosedur pada notasi Pseudocode dan Golang.

![Screenshot 2024-10-19 073104](https://github.com/user-attachments/assets/8d372240-a9a4-419b-a50f-df6751267617)

Penulisan deklarasi ini berada di luar blok yang dari program utama atau func main() pada suatu program Go dan bisa ditulis sebelum atau sete;ah dari blok program utama tersebut.
Contoh deklarasi prosedur mencetak n nilai pertama dari deret Fibonacci

![Screenshot 2024-10-19 073430](https://github.com/user-attachments/assets/6138906e-d47e-4fc6-8070-4633616257b5)

### 4.3 Cara Pemanggilan Procedure
Seperti yang sudah dijelaskan sebelumnya, suatu prosedur hanya akan dieksekusi apabila dipanggil bail secara langsung atau tidak oleh program utama. Tidak langsung di sini maksudnya adalah prosedur dipanggil oleh program utama melalui perantara subprogram yang lain.
Pemanggilan suatu prosedur cukup mudah, yaitu dengan hanya menuliskan nama beserta parameter atau argumen yang diminta dari suatu prosedur. Sebagai contoh prosedur cetak NFibo di atas dipanggil dengan menuliskan namanaya, kemudian sebuah variabel atau nilai integer tertentu sebagai argumen untuk parameter n. Contoh:

![Screenshot 2024-10-19 074030](https://github.com/user-attachments/assets/294413e2-2f8e-4342-9027-f44478bf1ef7)
![Screenshot 2024-10-19 074116](https://github.com/user-attachments/assets/32cec0d1-388a-489d-876b-296392f206cf)

Dari contoh di atas terlihat bahwa cara pemanggilan dengan notasi pseudocode dan GoLang adalah sama. Argumen yang digunakan untuk paramenter n berupa integer (sesuai deklarasi) yang terdapat pada suatu variabel (cara pemanggila n #1) atau nilainya secara lansung (cara pemanggilan #2).

### 4.4 Parameter
Suatu subprogram yang dipanggil dapat berkomunikasi dengan pemanggilnya melalui argumen yang diberikan melalui parameter yang dideklarasikan pada subprogramnya. Berikut ini jenis atau pembagian dari parameter.
Berdasarkan letak penulisannya pada program, maka parameter dapat dikelompokkan menjadi dua, yaitu parameter formal dan parameter aktual.

![Screenshot 2024-10-19 075144](https://github.com/user-attachments/assets/f91f649e-f859-4aa6-bb7c-83cb14c82dda)

1. Parameter Formal
   Parameter formal adalah parameter yang ditulis pada saat deklarasi suatu subprogram, parameter ini berfungsi sebagai petunjuk bahwa argumen apa saja yang diperlukan pada saat pemanggilan subprogram.
   Sebagai contoh parameter jari_jari, tinggi pada deklarasi fungsi volumeTabung adalah parameter formal. Artinya ketika memanggil volumeTabung maka kita harus mempersiapkan dua integer (berapapun nilainya) sebagai jari_jari dan tinggi.
2. Parameter Aktual
   Sedangkan parameter aktual adalah argumen yang digunakan pada bagian parameter saat pemanggilan suatu subprogram. Banyaknya argumen dan tipe data yang terdapat pada parameter aktual harus mengikuti parameter formal.
   Sebagai contoh argumen r, t, 15, 14, dan 200 pada contoh kode di atas adalah parameter aktual, yang menyatakan nilai yang kita berikan sebagai jari-jari dan tinggi. Selain itu parameter juga dikelompokkan berdasarkan alokasi memorinya, yaitu pass by value dan pass by reference.
1. Pass by Value
   Nilai parameter aktual akan disalin ke variabel lokal (parameter formal) pada subprogram. Artinya parameter aktual dan formal dialokasikan di dalam memori komputer dengan alamat memori yang berbeda. Subprogram dapat menggunakan nilai pada parameter formal tersebut untuk proses apapun, tetapi tidak dapat mengembalikan informasinya ke pemanggil melalui parameter aktual karena pemanggil tidak dapat mengakses memori yang digunakan oleh subprogram. Pass by value bisa digunakan baik oleh fungsi ataupun prosedur.
   Pada notasi pseudocode, secara semua parameter formal pada fungsi adalah pass by value, sedangkan pada prosedur diberi kata kunci in pada saat penulisan parameter formal. Sedangkan pada bahasa pemrograman Go sama seperti fungsi pada pseudocode, tidak terdapat kata kunci khusus untuk parameter formal fungsi dan prosedur.
2. Pass by Reference (Pointer)
   Ketika parameter didefinisikan sebagai pass by reference, maka pada saat pemanggilan parameter formal akan berperan sebagai pointer yang menyimpan alamat memori dari parameter aktual. Sehingga perubahan nilai yang terjadi pada parameter formal tersebut akan berdampak pada parameter aktual. Artinya nilai terakhirnya akan dapat diketahui oleh si pemanggil setelah subprogram tersebut selesai dieksekusi. Pass by reference sebaiknya digunakan hanya untuk prosedur.
   Penulisan parameter pass by reference pada prosedur baik pseudocode dan Go menggunakan kata kunci atau identifier khusus. Pada pseudocode menggunakan kata kunci in/out, sedangkan pada bahasa Go diberi identifier asterik (*) sebelum tipe data di parameter formal yang menjadi pass by reference.

Catatan: 
- Parameter pada fungsi sebaiknya adalah pass by value, hal ini dikarenakan fungsi bisa mengembalikan (return) nilai ke pemanggil dan tidak memberikan efek langsung pada program, walaupun tidak menutup kemungkinan menggunakan pass by reference.
- Penggunaan pass by reference sebaiknya pada prosedur karena prosedur tidak bisa mengembalikan nilai ke pemanggil. Dengan memanfaatkan pass by reference maka prosedur seolah-olah bisa mengirimkan nilai kepada si pemanggil. Untuk lebih jelas perhatikan contoh sebuah subprogram yang digunakan untuk menghitung persamaan berikut ini:

![Screenshot 2024-10-19 081031](https://github.com/user-attachments/assets/a3331540-d862-4116-add8-e2ba2cfb7a4d)

### II. GUIDED

# 1. Soal study Case
Berikut ini adalah contoh penulisan prosedur pada suatu program lengkap.
Buatlah sebuah program beserta prosedur yang digunakan untuk menampilkan suatu pesan error, warning atau informasi berdasarkan masukan dari user.
Masukan terdiri dari sebuah bilangan bulat flag ( 0 s.d. 2) dan sebuah string pesan M.
Keluaran berupa string pesan M beserta jenis pesannya, yaitu error, warning, atau informasi berdasarkan nilai flag 0, 1, dan 2 secara berturut-turut.

#### Source Code

#### Screenshot Output

#### Deskripsi Program

### III. UNGUIDED

# 1. Soal study case
Minggu ini, mahasiswa Fakultas Informatika mendapatkan tugas dari mata kuliah matematika diskrit untuk mempelajari kombinasi dan permutasi. Jonas salah seorang mahasiswa, iseng untuk mengimplementasikannya ke dalam suatu program. Oleh karena itu, bersediakan kalian membantu Jonas? (tidak tentunya ya :p)
Masukan terdiri dari empat buah bilangan asli a, b, c, dan d yang dipisahkan oleh spasi, dengan syarat a>=c dan b>=d
Keluaran terdiri atas dua baris. Baris pertama adalah hasil permutasi dan kombinasi a terhadap c, sedangkan baris kedua adalah hasil permutasi dan kombinasi b terhadap d.
Catatan: permutasi (P) dan kombinasi (C) dari n terhadap r (n>=r) dapat dihitung menggunakan persamaan berikut!

![Screenshot 2024-10-13 184052](https://github.com/user-attachments/assets/e706c426-eb47-4bab-aa9d-c0b89794268c)

contoh

![Screenshot 2024-10-13 184313](https://github.com/user-attachments/assets/4cc42d99-5d7c-4aed-a4d0-e58496301aa7)

![Screenshot 2024-10-13 184350](https://github.com/user-attachments/assets/e7b8cdd3-7871-44f0-a640-64edd27b4374)

#### Source Code

#### Screenshot Output

#### Deskripsi Program

# 2. Soal study case
Kompetisi pemrograman tingkat nasional berlangsung ketat. Setiap peserta diberikan 8 soal yang harus dapat diselesaikan dalam waktu 5 jam saja. Peserta yang berhasil menyelesaikan soal paling banyak dalam waktu paling singkat adalah pemenangnya.
Buat program gema yang mencari pemenang dari daftar peserta yang diberikan. Program harus dibuaat modular, yaotu dengan membuat prosedur hitungSkor yang mengembalikan total soal dan total skor yang dikerjakan oleh seorang peserta, melalui parameter formal. Pembacaan nama peserta dilakaukan di program utama, sedangkan waktu pengerjaan dibaca di dalam prosedur.
prosedure hitungSkor (in/out soal, skor : integer)
Setiap baris masukan dimulai dengan satu string nama peserta tersebut diikuti dengan adalah 8 integer yang menyatakan berapa lama (dalam menit) peserta tersebut menyelesaikan soal. Jika tidak berhasil atau tidak mengirimkan jawaban maka otomatis dianggap menyelesaikan dalam waktu 5 jam 1 menit (301 menit).
Satu baris keluaran berisi nama pemenang, jumlah soal yang diselesaikan, dan nilai yang diperoleh. Nilai adalah total waktu yang dibutuhkan untuk menyelesaikan soal yang berhasil diselesaikan.

![Screenshot 2024-10-19 083139](https://github.com/user-attachments/assets/c14b209c-eb60-454d-a13b-db51f30eee76)

Keterangan:
Astusi menyelesaikan 6 soal dalam waktu 287 menit, sedangkan Bertha 7 soal dalam waktu 294 menit. Karena menyelesaikan lebih banyak, maka Bertha menang. Jika keduanya menyelesaikan sama banyak, maka pemenang adalah yang menyelesaikan dengan total waktu paling kecil.

#### Source Code

#### Screenshot Output

#### Deskripsi Program

# 3. Soal study case
Skiena dan Ravilla dalam Programming Challenges mendefinisikan sebuah deret bilangan. Deret dimulai dengan sebuah bilangan bulat n. Jika bilangan n saat itu genap, maka suku berikutnya adalah 1/2n, tetapi jika ganjil maka suku berikutnya bernilai 3n+1. Rumus yang sama digunakan terus menerus untuk mencari suku berikutnya. Deret berakhir ketika suku terakhir bernilai 1. Sebagai contoh jika dimulai dengan n=22, maka deret bilangan yang diperoleh adalah:
22 11 34 17 52 26 13 40 20 10 5 1`6 8 4 2 1
Untuk suku awal sampai dengan 1000000, diketahui deret selalu mencapai suku dengan nilai 1. 
Buat program skiena yang akan mencetak setiap suku dari deret yang dijelaskan di atas untuk nilai suku awal yang diberikan. Pencetakan deret harus dibuat dalam prosedir cetakDeret yang mempunyai 1 parameter formal, yaitu nilai dari suku awal.
prosedure cetakDeret(in n : integer)
Masukan berupa satu bilangan integer positif yang lebih kecil dari 1000000
Keluaran terdiri dari satu baris saja. Setiap suku dari deret tersebut dicetak dalam baris yang dan dipisahkan oleh sebuah spasi.

![Screenshot 2024-10-19 084112](https://github.com/user-attachments/assets/65adf438-4685-414e-a70b-25b5706705f8)

#### Source Code

#### Screenshot Output

#### Deskripsi Program
