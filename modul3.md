<h1 align="center">LAPORAN PRAKTIKUM</h1>
<h2 align="center">ALGORITMA DAN PEMROGRAMAN 2</h2>

<h3 align="center">MODUL 3</h3>
<h4 align="center">FUNGSI</h4>

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


## I. DASAR TEORI

### 3.1 Definisi Function
Fungsi merupakan satu kesatuan rangkaian instruksi yang memberikan atau menghasilkan suatu nilai dan biasanya memetakkan input ke suatu  nilai yang lain. Oleh karena itu, fungsi selalu menghasilkan/mengembalikan nilai. Suatu subprogram dikatakan fungsi apabila:
1. Ada deklarasi tipe nilai yang dikembalikan, dan
2. Terdapat kata kunci return dalam badan subprogram
Maka fungsi digunakan jika suatu nilai biasanya diperlukan, seperti:
- Assignment nilai ke suatu variabel
- Bagian dari ekspresi
- Bagian dari argumen suatu subprogram, dsb
Karena itu selalu pilih nama fungsi yang menggambarkan nilai, seperti kata benda dan kata sifat. Contoh nama-nama fungsi: median, rerata, nilaiTerbesar, ketemu, selesai, ...

### 3.2 Deklarasi Function
Deklarasi fungsi sama dengan prosedur, yaitu berada pada blok yang terpisah dengan program utama

![Screenshot 2024-10-12 072636](https://github.com/user-attachments/assets/9f4206ab-8148-40d0-880f-fe9b86903dcd)

Pada bagian deklarasi terlihat setelah parameter terdapat tipe naam data dari nilai yang dikembalikan, sedangkan pada bagian fungsi badann fungsi terdapat return dari nilai yang dikembalikan. 
Berikut adalah contoh fungsi untuk menghitung volume dari tabung apabila jari-jari alas dan tinggi tabung diketahui.

![Screenshot 2024-10-12 072934](https://github.com/user-attachments/assets/575ab68f-0834-4bcb-b3f5-ee83f5d7d9e0)

### 3.3 Cara Pemanggilan Function
Sama halnya dengan prosedur, pemanggilan fungsi cukup dilakukan dengan penulisan nama fungsi beserta argumen yang diminta oleh parameter dari fungsi. Perbedaannya dengan prosedur adalah fungsi bisa di-assign ke suatu variabel, menjadi bagian dari ekpresi, dan argumen dari suatu subprogram.

![Screenshot 2024-10-12 073251](https://github.com/user-attachments/assets/cfe7d028-cc8c-4b6f-9a10-6448fe866e45)


![Screenshot 2024-10-12 073335](https://github.com/user-attachments/assets/dc5049ff-59af-4f4e-ab3e-c8b7a6ce6375)

Pada contoh pemanggilan fungsi diatas terlihat tidak ada perbedaan pada saat pemanggilan fungsi pada pseudecode ataupun GoLang. Disini terlihat fungsi bisa di-assign ke suatu variabel pada saar pemanggilan, bisa dioperasikan sesuai dengan tipe data yang dikembalikan dan juga bisa langsung ditampilkan dengan perintah output ataupun print.

### GUIDED

Berikut ini adalah contoh penulisan fungsi pada suatu program lengkap.
Bautlah sebuah
