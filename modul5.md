<h1 align="center">LAPORAN PRAKTIKUM</h1>
<h2 align="center">ALGORITMA DAN PEMROGRAMAN 2</h2>

<h3 align="center">MODUL 5</h3>
<h4 align="center">REKURSIF</h4>

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

### 5.1 Pengantar Rekursif
Pada modul-modul sebelumnya sudah dijelaskan bahwa suatu subprogram baik fungsi atau prosedur bisa memanggil subprogram lainnya. Hal ini tidak menutup kemungkinan bahwa subprogram yang dipanggil adalah dirinya sendiri. Dalam pemrograman teknik ini dikenal dengan istilah rekursif. Rekursif secara sederhana dapat diartikan sebagai cara menyelesaikan suatu masalah dengan cara menyelesaikan sub-masalah yang identik dari masalah utama. Sebagai contoh perhatikan prosedur cetak berikut ini.

![Screenshot 2024-10-31 082115](https://github.com/user-attachments/assets/fb640804-fbcf-4b7d-bd73-dbedcabc0e8f)

Apabila diperhatikan subprogram cetak() di atas, terlihat pada baris ke-4 terdapat pemanggilan subprogram cetak() kembali. Misalnya apabila kita eksekusi perintah cetak(5) maka akan menampilkan angka 5 6 7 8 9 ...dst tanpa henti. Artinya, setiap pemanggilan subprogram cetak() nilai x akan selalu bertambah 1 (increment by one) secara terus menerus tanpa henti.

![Screenshot 2024-10-31 082527](https://github.com/user-attachments/assets/4706374c-da41-4b65-ab7e-4e45457cf70a)

Oleh karena itu biasanya ditambahkan struktur kontrol percabangan (if-then) untuk menghentikan proses rekursif ini. Kondisi ini disebut juga dengan base-case, artinya apabila kondisi base-case bernilai true maka proses rekursif akan berhenti. Sebagai contoh misalnya base case adalah ketika x bernilai 10 atau x == 10, maka tidak perlu dilakukan rekursif.

![Screenshot 2024-10-31 082747](https://github.com/user-attachments/assets/17a57279-6f1d-4a7f-b27b-312faf150cf5)

Apabila diperhatikan pada baris ke-3 di Program di atas, kita telah menambahkan base-case seperti penjelasan sebelumnya. Selanjutnya pada bagian aksi dari else di baris ke-6 dan ke-7 kita namakan recursive-case atau kasus pemanggilan dirinya sendiri tersebut terjadi. Kondisi dari recursive-case ini adalah negasi dari kondisi base-case atau ketika nilai x != 10.

![Screenshot 2024-10-31 083020](https://github.com/user-attachments/assets/72e14f5d-c54a-48e9-9e2a-ab49ae600a5e)

Apabila program di atas ini dijalankan maka akan tampil angka 5 6 7 8 9 10. Terlihat bahwa proses rekursif berhasil dihentikan ketika x == 10.

![Screenshot 2024-10-31 083138](https://github.com/user-attachments/assets/70c26df2-6513-4542-aa52-bd31a056037b)

Pada gambar memperlihatkan saat subprogram dipanggil secara rekursif, maka subprogram akan terus melakukan pemanggilan (forward) hingga berhenti pada saat kondisi base-case terpenuhi atau true. Setelah itu akan terjadi proses backward atau kembali ke subprogram yang sebelumnya. Artinya setelah semua instruksi cetak(10) selesai dieksekusi, maka program akan kembali ke cetak(9) yang memanggil cetak (10) tersebut. Begitu seterusnya hingga kembali ke cetak(5).

Perhatikan modifikasi program di atas dengan menukar posisi baris 10 dan 11, mengakibatkan ketika program dijalankan maka akan menampilkan 10 9 8 7 6 5. Kenapa bisa demikian? Pahami proses backward pada gambar.

![Screenshot 2024-10-31 083615](https://github.com/user-attachments/assets/7ce96e7c-df00-4ee5-b307-a9973779983a)

### Catatan
- Teknik rekursif ini merupakan salah satu alternatif untuk mengganti struktur kontrol perulangan dengan memanfaatkan subprogram (bisa fungsi ataupun prosedure).
- Untuk menghentikan proses rekursif digunakan percabangan (if-then)
- Base-case adalah kondisi proses rekursif berhenti. Base-case merupakan hal terpenting dan pertama yang harus diketahui ketika akan membuat program rekursif. Mustahil membuat program rekursif tanpa mengetahui base-case terlebih dahulu.
- Recursive-case adalah kondisi dimana proses pemanggilan dirinya sendiri dilakukan. Kondisi recursive-case adalah komplemen atau negasi dari base-case.
- Setiap algoritma rekursif selalu memiliki padanan dalam bentuk algoritma interatif.

### 5.2 Komponen Rekursif

Algoritma rekursif terdiri dari dua komponen utama:

- Base-case (Basis), yaitu bagian untuk menghentikan proses rekursif dan menjadi komponen terpenting di dalam sebuah rekursif
- Recursive-case, yaitu bagian pemanggilan subprogramnya.

### 5.3 Control Program dengan menggunakan Rekursif

a. Membuat baris bilangan dari n hingga 1
Base-case: bilangan == 1

![Screenshot 2024-10-31 084412](https://github.com/user-attachments/assets/3a5cacbe-3f00-482a-b6d6-7ba99a11c76c)

b. Menghitung hasil penjumlahan 1 hingga n
Base-case: n == 1

![Screenshot 2024-10-31 084517](https://github.com/user-attachments/assets/d5134a44-949e-408d-b4af-2bf5dee65d72)

c. Mencari dua pangkat n
Base-case: n == 0

![Screenshot 2024-10-31 084629](https://github.com/user-attachments/assets/6b9a7c3b-ba6d-4af2-aa81-80bbf5191f5a)

d. Mencari nilai faktorial atau n!
Base-case: n == 0 atau n == 1

![Screenshot 2024-10-31 084817](https://github.com/user-attachments/assets/7327b33a-d125-41e4-9ca7-d3358215530b)

### II. GUIDED

# 1. Soal study Case
# Source Code
```go
package main

import "fmt"

// Fungsi untuk mencetak bilangan dari n hingga 1
func cetakMundur(n int) {
	if n -- 1 {
		return
	}
	fmt.Print(n, " ")
	cetakMundur(n - 1)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai n untuk cetak bilangan dari n hingga 1: ")
	fmt.Scanln(&n)
	fmt.Print("Hasil cetak mundur: ")
	cetakMundur(n)
}
```
# Screenshot Output

# Deskripsi Program

# 2. Soal study Case
# Source Code
```go
package main

import "fmt"

// Fungsi untuk menghitung penjumlahan 1 hingga n
func jumlahRekursif(n int) int {
	if n -- 1 {
		return 1
	}
	return n + jumlahRekursif(n-1)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai n untuk penjumlahan 1 hingga n : ")
	fmt.Scanln(&n)
	fmt.Println("Hasil penjumlahan:", jumlahRekursif(n))
}
```
# Screenshot Output
# Deskripsi Program

# 3. Soal study Case
# Source Code
```go
package main

import "fmt"

// Fungsi untuk mencari 2 pangkat n
func pangkatDua(n int) int {
	if n -- 0 {
		return 1
	}
	return 2 * pangkatDua(n-1)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai n untuk mencari 2 pangkat n: ")
	fmt.Scanln(&n)
	fmt.Println("Hasil 2 pangkat", n, ":", pangkatDua(n))
}
```
# Screenshot Output
# Deskripsi Program

# 4. Soal study Case
# Source Code
```go
package enam

import "fmt"

// Fungsi untuk menghitung faktorial n!
func faktorial(n int) int {
	if n -- 0 || n -- 1 {
		return 1
	}
	return n * faktorial(n-1)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai n untuk mencari faktorial n!: ")
	fmt.Scanln(&n)
	fmt.Println("Hasil faktorial dari", n, ":", faktorial(n))
}
```
# Screenshot Output

# Deskripsi Program

### III. UNGUIDED

# 1. Soal study Case
Deret fibonacci adalah sebuah deret dengan nilai suku ke-0 dan ke-1 adalah 0 dan 1, dan nilai suku ke-n selanjutnya adalah hasil penjumlahan dua suku sebelumnya. Secara umum dapat diformulasikan Sn =Sn-1 + Sn-2. Berikut ini adalah contoh nilai deret fibonacci hingga suku ke-10. Buatlah program yang mengimplementasikan fungsi rekursif pada deret fibonacci tersebut.

![Screenshot 2024-10-31 085305](https://github.com/user-attachments/assets/76164738-45af-4c38-9a24-77da37d4a8f9)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func fibonacci(n int) int {
	if n <= 1 {
		return n
	}
	return fibonacci(n-1) + fibonacci(n-2)
}

func main() {
	var n int
	fmt.Print("Masukkan nilai n (indeks deret Fibonacci): ")
	fmt.Scanln(&n)

	hasil := fibonacci(n)
	fmt.Printf("Nilai Fibonacci ke-%d adalah: %d\n", n, hasil)
}
```
# Screenshot Output

![Screenshot 2024-10-31 211526](https://github.com/user-attachments/assets/b243d9ed-4ca8-4206-888c-866b92383adf)

# Deskripsi Program

Program ini menghitung nilai Fibonacci pada indeks tertentu menggunakan rekursi di bahasa Go. 

1. **Fungsi `fibonacci`**: Mengembalikan nilai Fibonacci untuk indeks `n` menggunakan rekursi (F(n) = F(n-1) + F(n-2)).
2. **Fungsi `main`**: Meminta pengguna memasukkan nilai `n`, lalu menampilkan nilai Fibonacci ke-`n` yang dihitung.

**Contoh Output**:
Jika `n = 5`, output akan menjadi:  
`Nilai Fibonacci ke-5 adalah: 5`

# 2. Soal study Case
Buatlah sebuah program yang digunakan untuk menampilkan pola bintang berikut ini dengan menggunakan fungsi rekursif. N adalah masukan dari user.

![Screenshot 2024-10-31 085448](https://github.com/user-attachments/assets/9682a3b3-a9c0-4052-835d-04efc43ab6d6)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func printStars(n int) {
	if n == 0 {
		return
	}
	printStars(n - 1)
	for i := 0; i < n; i++ {
		fmt.Print("*")
	}
	fmt.Println()
}

func main() {
	var n int
	fmt.Print("Masukkan jumlah baris bintang: ")
	fmt.Scanln(&n)

	printStars(n)
}
```
# Screenshot Output

![Screenshot 2024-10-31 211747](https://github.com/user-attachments/assets/92ffbf7c-040b-4343-94e1-ae165886544c)

# Deskripsi Program

Program ini mencetak pola segitiga bintang menurun menggunakan rekursi di bahasa Go. Pengguna memasukkan jumlah baris, dan program menampilkan bintang secara bertahap dari satu bintang di baris pertama hingga sejumlah `n` bintang di baris terakhir.

# 3. Soal study Case
Buatlah program yang mengimplementasikan rekursif untuk menampilkan faktor bilangan dari suatu N atau bilangan yang apa saja habis membagi N.
Masukan terdiri dari sebuah bilangan bulat positif N
Keluaran terdiri dari barisan bilangan yang menjadi faktor dari N (terurut dari 1 hingga N ya)

![Screenshot 2024-10-31 085729](https://github.com/user-attachments/assets/4f3ff623-46b3-4a9d-8888-39243af18a6b)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func isFaktor(bilangan, faktor int) bool {
        return bilangan%faktor == 0
}

func cetakFaktor(bilangan, faktor int) {
        if faktor > bilangan {
                return
        }
        if isFaktor(bilangan, faktor) {
                fmt.Print(faktor, " ")
        }
        cetakFaktor(bilangan, faktor+1)
}

func main() {
        var bilangan int
        fmt.Print("Masukkan bilangan: ")
        fmt.Scanln(&bilangan)

        fmt.Printf("Faktor dari %d adalah: ", bilangan)
        cetakFaktor(bilangan, 1)
        fmt.Println()
}
```
# Screenshot Output

![Screenshot 2024-10-31 211917](https://github.com/user-attachments/assets/b09642b0-93f2-4ad4-8b8c-17b51f99fcb8)

# Deskripsi Program

Program ini mencetak semua faktor dari sebuah bilangan menggunakan rekursi di bahasa Go. Pengguna memasukkan bilangan, dan program menampilkan faktor-faktor bilangan tersebut satu per satu.

Fungsi isFaktor: Memeriksa apakah faktor adalah faktor dari bilangan.
Fungsi cetakFaktor: Mencetak faktor-faktor dari bilangan secara rekursif, mulai dari 1 hingga bilangan itu sendiri.

# 4. Soal study Case
Buatlah program yang mengimplementasikan rekursif untuk menampilkan barisan bilangan tertentu.
Masukan terdiri dari sebuah bilangan bulat positif N
Keluaran terdiri dari barisan dari N hingga 1 dan kembali ke N

![Screenshot 2024-10-31 181453](https://github.com/user-attachments/assets/bbaa9e50-1ea5-43e4-b47e-a2322c6a94e4)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func printSequence(n int) {
	if n == 0 {
		return
	}
	fmt.Print(n, " ")
	printSequence(n - 1)
	fmt.Print(n, " ")
}

func main() {
	var n int
	fmt.Print("Masukkan nilai N: ")
	fmt.Scanln(&n)

	fmt.Println("Barisan bilangan:")
	printSequence(n)
}
```
# Screenshot Output

![Screenshot 2024-10-31 212042](https://github.com/user-attachments/assets/7a5a9fb2-0c4a-476c-86c6-0f4d9e3bc09d)

# Deskripsi Program


Program ini mencetak barisan bilangan secara rekursif yang menurun dari n ke 1 dan kemudian naik kembali ke n. Pengguna memasukkan nilai n, dan program menampilkan barisan angka tersebut.

# 5. Soal study Case
Buatlah program yang mengimplementasikan rekursif untuk menampilkan barisan bilangan ganjil.
Masukan terdiri dari sebuah bilangan bulat positif
Keluaran terdiri dari barisan bilangan ganjil dari 1 hingga N

![Screenshot 2024-10-31 181646](https://github.com/user-attachments/assets/796a1860-9f16-4e5c-8d7d-b28cb568243f)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func main() {
	var n int
	fmt.Print("Masukkan bilangan bulat positif N: ")
	fmt.Scanln(&n)

	fmt.Println("Barisan bilangan ganjil:")
	cetakGanjil(1, n)
}

func cetakGanjil(i int, n int) {
	if i > n {
		return
	}
	fmt.Print(i, " ")
	cetakGanjil(i+2, n)
}
```
# Screenshot Output

![Screenshot 2024-10-31 215509](https://github.com/user-attachments/assets/9e2c0654-0665-4883-a4ba-913cd95e74a2)

# Deskripsi Program


Program ini mencetak barisan bilangan ganjil dari 1 hingga bilangan N menggunakan rekursi. Pengguna memasukkan bilangan positif N, dan program menampilkan bilangan ganjil secara bertahap hingga mencapai atau mendekati N.

# 6. Soal study Case
Buatlah program yang mengimplementasikan rekursif untuk mencari hasil pangkat dari dua buah bilangan
Masukan terdiri dari bilangan bulat x dan y
Keluaran terdiri dari hasil x dipangkatkan y
Catatan: diperbolehkan menggunakan asterik "*", tapi dilarrang menggunakan import "math"

![Screenshot 2024-10-31 181900](https://github.com/user-attachments/assets/1e7f1461-685e-48c6-9411-9953755044cd)

# Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06
package main

import "fmt"

func pangkat(x, y int) int {
	if y == 0 {
		return 1
	}
	return x * pangkat(x, y-1)
}

func main() {
	var x, y int

	fmt.Println("Masukkan bilangan dasar (x):")
	fmt.Scanln(&x)
	fmt.Println("Masukkan pangkat (y):")
	fmt.Scanln(&y)

	hasil := pangkat(x, y)
	fmt.Printf("%d pangkat %d adalah: %d\n", x, y, hasil)
}
```
# Screenshot Output

![Screenshot 2024-10-31 215724](https://github.com/user-attachments/assets/aad485ae-5507-4e60-b11f-7172cb38262b)

# Deskripsi Program


Program ini menghitung hasil perpangkatan menggunakan rekursi. Pengguna memasukkan bilangan dasar x dan pangkat y, lalu program menampilkan hasil x pangkat y.
