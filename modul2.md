<h1 align="center">LAPORAN PRAKTIKUM</h1>
<h2 align="center">ALGORITMA DAN PEMROGRAMAN 2</h2>

<h3 align="center">MODUL 2</h3>
<h4 align="center">REVIEW STRUKTUR KONTROL</h4>

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

### 2.1 Struktur Program Go
Dalam kerangka program yang ditulis dalam bahasa pemrograman Go, program utama selalu mempunyai dua komponen berikut:

- package main merupakan penanda bahwa file ini berisi program utama
- func main() berisi kode utama dari sebuah program Go
Komentar, bukan bagian dari kode program  dan dapat ditulis dimana saja di dalam program:
- satu baris teks yang diawali dengan garis miring ganda (//) s.d. akhir baris, atau
- beberapa baris teks yang dimulai dengan pasangan karakter '/*' dan di akhiri dengan '*/'.

### 1. Koding, Kompilasi, dan Eksekusi Go
# Koding
- Tidak berbeda dengan penulisan program sumber dalam bahasa lain, program Go harus dibuat dengan menggunakan penyuntingan teks dan disimpan dalam format teks, bukan dalam format dokumen (doc, docx, atau lainnya)
- Setiap program go disimpan dalam file teks dengan ekstensi *.go, dengan nama bebas. Sebaiknya nama file adalah nama untuk program tersebut
- Setiap satu program lengkap Go disimpan dalam satu folder tersendiri. Nama folder merupakan nama program tersebut. Karena itu secara prinsip, satu program Go dapat dipecah dalam beberapa file dengan esktensi *.go selama disimpan dalam folder yang sama.
# Kompilasi
Beberapa bahasa pemmrograman dirancang untuk diimplementasikan sebagai interpreter dan lainnya sebagai kompilator. Interpreter akan membaca setiap baris instruksi dan kemudian langsung mengeksekusinya, dengan hanya sedikit pemeriksaan apakah penulisan keseluruhan program sudah benar atau belum. Kompilator akan memeriksa keseluruhan program sumber dan kemudian mengubahnya menjadi program eksekutabel, sehingga konsistensi penulisan (seperti penggunaan tipe data) sudah diperiksa sebelum dieksekusi. Selain itu karena program dibuat menjadi eksekutabel lebih dahulu, proses optimasi dapat dilakukan sehingga program menjadi sangat efisien.
Go diimplementasikan sebagai kompilator. Berikut adalah contoh sesi yang biasa dilakukan saat mengkompilasi dan mengeksekusi program dalam bahasa Go:

- Panggil shell atau terminal (program/utiliti cmd.exe di windows)
- Masuk ke dalam (cd) folder program (normalnya ada di C:\Users\go\src\ atau yang sejenisnya)\
- Kemudian panggil perintah go build atau go build file.go untuk mengkompilasi file.go
- Jika gagal, akan muncul pesan eror yang sesuai, pelajari dengan baik pesan tersebut, perbaiki teks program sumber, kemudian ulangi proses build-nya
- Jika berhasil, maka pada folder tersebut akan dibuat program dengan nama yang sama dan diakhiri dengan .exe (untuk windows)
- Panggil progra, eksekutabel tersebut dari terminal yang sama. Jangan memanggil program tersebut dengan mengklik eksekutabel tersebut dari folder karena program kalian hanya berbasis teks, bukan/belum dirancang dengan tampilan windows.

# Catatan
Semua proses terkait bahasa Go dilakukan melalui utilitas go. Beberapa opsi dengan utilitas go:

- go build: mengkompilasi program sumber yang ada dalam folder menjadi sebuah program
- go build file.go: mengkompilasi program sumber file.go saja
- go fmt: membaca semua program sumber dalam folder dan mereformat penulisannya agar sesuai dengan standar penulisan program sumber Go.
- go clean: membersihkan file-file dalam folder sehingga tersisa program sumbernya saja.

### 2.2 Tipe Data dan Instruksi Dasar
# 1. Data dan Variabel
Variabel adalah nama dari suatu lokasi di memori, yang data dengan tipe tertentu dapat disimpan

- Nama variabel dimulai dengan huruf dan dapat diikuti dengan sejumlah huruf, angka, atau garis bawah.
- Tipe data yang umum tersedia adalah integer, real, boolean, karakter, dan string. Lihat tabel berikut ini untuk variasi tipe data yang disediakan dalam bahasa Go
- Nilai data yang tersimpan dalam variabel dapat diperoleh dengan menyebutkan langsung nama variabelnnya
contoh: menyebutkan nama found akan mengambil nilai tersimpan dalam memori untuk variabel found, pastinya.
- Informasi alamat atau lokasi dari variabel dapat diperoleh dengan menambahkan prefiks & di depan nama variabel tersebut
contoh: &found akan mendapatkan alamat memori untuk menyimpan data pada found
- Jika variabel berisi alamat memori, prefiks * pada variabel tersebut akan memberikan nilai yang tersimpan dalam memori yang lokasinya disimpan dalam variabel tersebut
contoh: *mem akan mendapatkan data di memori yang alamatnya tersimpan di mem, karenanya *(&found) akan mendapatkan data dari lokasi memori variabel found berada, alias sama saja dengan menyebutkan langsung found 8=)
- Operasi yang dapat dilakukan terhadap tipe data diatas adalah
<img width="318" alt="ssmaterigo" src="https://github.com/user-attachments/assets/e8aaa0ee-e126-4a17-8b90-85c978cf2ff9">
Contoh:
![Screenshot 2024-10-06 163404](https://github.com/user-attachments/assets/fa35f401-47b4-4ee6-b5dd-b8c233ea193c)
- Bahasa Go menganut kesesuaian tipe data yang ketat. Tipe data yang berbeda tidak boleh dicampur dalam satu ekspresi, bahkan tipe data masih yang sejenis, misalnya masih sama-sama integer (int dan int32). Untuk menyesuaikan tipe data, ada beberapa cara yang dapat dilakukan:
    - Casting, tipe (data), mengubah tipe dari data yang diberikan ke tipe yang diinginkan
    - Memanfaatkan fungsi Sprint dan Sscan dari paket fmt.
    - Memanfaatkan fungsi-fungsi dalam paket strconv, seperti Atol, Itoa, dan ParseBool. Lihat lampiran berikut untuk contoh penggunaan.
      ![Screenshot 2024-10-06 163905](https://github.com/user-attachments/assets/db51abfc-c14b-4d8a-a3f9-c9bbdb16beab)
  - Variabel harus dideklarasikan dulu sebelum digunakan. Variabel juga harus diinisialisasi dulu (diisi data) agar nilai yang tersimpan diketahui dengan jelas dan eksekusi algoritma menjadi terprediksi. Dalam bahasa Go, variabel yang tidak diinisialisasi lebih dulu otomatis diisi dengan nilai default yang ekuivalen dengan bit 0.
    * Nilai 0 untuk bilangan integer
    * 0.0E+0 untuk bilangan real
    * false untuk boolean
    * karakter NUL (lihat tabel ASCII) untuk karakter
    * ''''(string kosong, string dengan panjang 0) untuk string
    * nill untuk alamat memori
    ![Screenshot 2024-10-06 164325](https://github.com/user-attachments/assets/37e16ac3-e7fd-445f-9d19-24cd640aee6c)

# 2. Instruksi Dasar
 ![Screenshot 2024-10-06 173558](https://github.com/user-attachments/assets/be3fb07e-6c08-44e3-9fe2-33ca22efdf25)
![Screenshot 2024-10-06 173623](https://github.com/user-attachments/assets/efc8cdf9-6eb4-4f51-bd7b-0dbfade3f02e)

# 3. Konstanta Simbolik
Konstanta dapat diberi nama untuk memudahkan mengingat maksud dan manfaat dari nilai yang diberi nama tersebut. 
![Screenshot 2024-10-06 173830](https://github.com/user-attachments/assets/c2638880-b2e4-43b5-8de3-c560413dd8eb)

### 2.3 Struktur Kontrol Perulangan
Go hanhya mempunyai kata kunci for untuk semua jenis perulangan yang kita pelajari dalam kondisi notasi algoritma. Dua bentuk yang kita gunakan disini adalah struktur while-loop dan repeat-until.
![Screenshot 2024-10-06 180629](https://github.com/user-attachments/assets/9246f2bd-9794-451c-a2e7-a17bdcaf8d3c)
Dalam konsep pemrograman terstruktur, setiap rancangan algoritma harus memenuhi syarat satu pintu masuk dan satu pintu keluar. Karena itu tidaklah diperkenankan untuk membuat program sumber yang mempunyai struktur loop yang mempunyai pintu keluar lebih dari satu, seperti:
- Satu pintu keluar dari kondisi for dan satu lagi dari instruksi if-break
- Atau mempunyai isntruksi if-break yang lebih dari satu
1. Bentuk While-Loop
   Bentuk While-Loop memastikan setiap kali memasuki loop, ada kondisi yang harus terpenuhi (benar/true). Ini juga berarti saat keluar dari loop, maka nilai kondisi tersebut pasti salah/false!
 ![Screenshot 2024-10-06 181927](https://github.com/user-attachments/assets/3d741a47-88e5-46b8-a426-592b376e5637)
 ![Screenshot 2024-10-06 182025](https://github.com/user-attachments/assets/2d48f109-8443-4ef8-8ae8-eade308307b0)

2. Bentuk Repeat-Until
   Bentuk repeat-until di perulangan dilakukan terus menerus sampai kondisi keluar terpenuhi. Artinya selama kondisi belum terpenuhi (salah/false) maka perulangan akan terus dilakukan. Pada saat keluar dari loop maka nilai kondisi pasti benar/true!
 ![Screenshot 2024-10-06 182535](https://github.com/user-attachments/assets/7ac3e011-3004-476d-812b-a6cd1d06698f)
Perhatian: Karena pernyataan kondisi ada di bawah pada bentuk repeat-until, apapun kondisinya, badan loop pasti akan pernah dieksekusi minimum satu kali.
Kode Go di bawah menggunakan algoritma yang sangat mirip dengan algoritma di atas, dengan perbedaan pada digunakannya bentuk while-loop. Umumnya keluaran kedua algoritma sama, kecuali saat maxF diisialisasi dengan nilai 0 atau lebih kecil.
![Screenshot 2024-10-06 183256](https://github.com/user-attachments/assets/9f9fbb25-53f1-4265-ae2e-4e91b9264be1)

## II. GUIDED
