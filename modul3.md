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


### I. DASAR TEORI

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

### II. GUIDED

# 1. Soal study Case
Berikut ini adalah contoh penulisan fungsi pada suatu program lengkap.
Buatlah sebuah program beserta fungsi yang digunakan untuk menghitung nilai faktorial dan permutasi.
Masukan terdiri dari dua buah bilangan positif a dan b
Keluaran berupa sebuah bilangan bulat yang menyatakan nilai a permutasi b apabila a>=b atau b permutasi a untuk kemungkinan yang lain.

#### Source Code
```go
package main

import "fmt"

func main() {
	var a, b int
	fmt.Scan(&a, &b)
	if a >= b {
		fmt.Println(permutasi(a, b))
	} else {
		fmt.Println(permutasi(b, a))
	}
}
func faktorial(n int) int {
	var hasil int = 1
	var i int
	for i = 1; i <= n; i++ {
		hasil = hasil * i
	}
	return hasil
}
func permutasi(n, r int) int {
	return faktorial(n) / faktorial(n-r)
}
```
#### Screenshot Ouput

![Screenshot 2024-10-13 191551](https://github.com/user-attachments/assets/53e1706e-f48e-4696-8575-acf51ed00527)

#### Deskripsi Program

Program ini ditulis dalam bahasa Go untuk menghitung permutasi dari dua bilangan bulat yang dimasukkan oleh pengguna. Setelah membandingkan kedua angka, program menghitung permutasi menggunakan rumus \( P(n, r) = \frac{n!}{(n-r)!} \) dan menampilkan hasilnya. Fungsi faktorial digunakan untuk menghitung nilai yang diperlukan dalam perhitungan.

# 2. Soal study case
Buatlah program untuk menghitung luas permukaan alas dan volume balok

#### Source Code
```go
package main

import "fmt"

func hitungLuasPermukaan(panjang, lebar, tinggi int) int {
	return 2 * (panjang*lebar + panjang*tinggi + lebar*tinggi)
}
func hitungVolume(panjang, lebar, tinggi int) int {
	return panjang + lebar + tinggi
}
func main() {
	var panjang, lebar, tinggi int

	fmt.Println("Masukkan panjang balok: ")
	fmt.Scan(&panjang)
	fmt.Println("Masukkan lebar balok: ")
	fmt.Scan(&lebar)
	fmt.Println("Masukkan tinggi balok: ")
	fmt.Scan(&tinggi)

	luasPermukaan := hitungLuasPermukaan(panjang, lebar, tinggi)
	volume := hitungVolume(panjang, lebar, tinggi)

	fmt.Printf("Luas permukaan balok: %d\n", luasPermukaan)
	fmt.Printf("Volume balok: %d\n",volume)
}
```

#### Screenshot Ouput

![Screenshot 2024-10-13 191332](https://github.com/user-attachments/assets/6e526ec3-295e-4a2f-8a70-6ab7418659fd)

#### Deskripsi Program

Program Go ini menghitung luas permukaan dan volume balok. Pengguna memasukkan panjang, lebar, dan tinggi.

## III. UNGUIDED

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
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06

package main

import "fmt"

var a, b, c, d int

// Fungsi untuk menghitung faktorial dari bilangan n
func faktorial(n int) int {
	hasil := 1
	// Loop untuk menghitung faktorial, dimulai dari 1 hingga n
	for i := 1; i <= n; i++ {
		hasil = hasil * i
	}
	return hasil
}

// Fungsi untuk menghitung permutasi P(n, r) = n! / (n-r)!
func permutasi(n, r int) int {
	return faktorial(n) / faktorial(n-r)
}

// Fungsi untuk menghitung kombinasi C(n, r) = n! / (r! * (n-r)!)
func kombinasi(n, r int) int {
	return faktorial(n) / (faktorial(r) * faktorial(n-r))
}

func main() {

	fmt.Print("Masukkan input = ")
	fmt.Scan(&a, &b, &c, &d)

	if a >= c && b >= d {
		// Baris pertama: Permutasi dan Kombinasi a terhadap c
		fmt.Printf("%d, %d\n", permutasi(a, c), kombinasi(a, c))

		// Baris kedua: Permutasi dan Kombinasi b terhadap d
		fmt.Printf("%d, %d\n", permutasi(b, d), kombinasi(b, d))
	} else {
		fmt.Println("Syarat tidak terpenuhi: a harus >= c dan b harus>=d")
	}
}
```

#### Screenshot Output

![Screenshot 2024-10-13 190341](https://github.com/user-attachments/assets/2091e9f6-d55b-456f-8a96-495bf96e7031)

#### Deskripsi Program

Program ini ditulis dalam bahasa Go untuk menghitung permutasi dan kombinasi berdasarkan empat bilangan bulat yang dimasukkan pengguna: `a`, `b`, `c`, dan `d`. 

Jika `a` lebih besar atau sama dengan `c` dan `b` lebih besar atau sama dengan `d`, program akan menghitung dan menampilkan permutasi dan kombinasi untuk pasangan `(a, c)` dan `(b, d)`. Jika syarat tidak terpenuhi, program akan menampilkan pesan kesalahan. Program ini menggabungkan fungsi faktorial, permutasi, dan kombinasi dalam satu aplikasi.

# 2. Soal study case
Diberikan tiga buah fungsi yaitu 

![Screenshot 2024-10-13 184544](https://github.com/user-attachments/assets/b2bdc4f6-a07c-42ff-ab61-5f6de40261b9)

Fungsi komposisi (fogoh) artinya adalah f(g(h(x))). Tuliskan f(x), g(x), dan h(x) dalam bentuk function.
Masukan terdiri dari sebuah bilangan bulat a, b, dan c yang dipisahkan oleh spasi
Keluaran terdiri dari tiga baris. Baris pertama adalah (fogoh)(a), baris kedua (gohof)(b)dan baris ketiga (hofog)(c)!
contoh:

![Screenshot 2024-10-13 184822](https://github.com/user-attachments/assets/5ca83c56-34f2-4f3e-af1c-a37cf24ada7d)

#### Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06

package main

import "fmt"

func f(x int) int {
	return x * x
}

func g(x int) int {
	return x - 2
}

func h(x int) int {
	return x + 1
}

func fogoh(x int) int {
	return f(g(h(x)))
}

func gohof(x int) int {
	return g(h(f(x)))
}

func hofog(x int) int {
	return h(f(g(x)))
}

func main() {
	var a, b, c int

	fmt.Scanf("%d %d %d", &a, &b, &c)

	fmt.Printf("fogoh(%d) = %d\n", a, fogoh(a))
	fmt.Printf("gohof(%d) = %d\n", b, gohof(b))
	fmt.Printf("hofog(%d) = %d\n", c, hofog(c))
}
```

#### Screenshot Output

![Screenshot 2024-10-13 190557](https://github.com/user-attachments/assets/6ea93a84-9f4b-47d8-a77f-e356b868498c)

#### Deskripsi Program

Program Go ini melakukan komposisi fungsi matematis. 

1. **Fungsi**: Terdapat tiga fungsi dasar (`f`, `g`, `h`) dan tiga fungsi komposisi (`fogoh`, `gohof`, `hofog`).
2. **Input**: Pengguna memasukkan tiga bilangan bulat: `a`, `b`, dan `c`.
3. **Output**: Program mencetak hasil komposisi fungsi untuk nilai `a`, `b`, dan `c`.

Program ini menunjukkan penerapan komposisi fungsi dalam pemrograman.

# 3. soal study case
[Lingkaran] Suatu lingkaran didefinisikan dengan koordinat titik pusat (cx, cy) dengan radius r, apabila diberikan dua buah lingkaran, maka tentukan posisi sebuah titik sembarang (x, y) berdasarkan dua lingkaran tersebut.
Masukan terdiri dari beberapa tiga baris. Baris pertama dan kedua adalah koordinat titik pusat dan radius dari lingkaran 1 dan lingkaran 2, sedangkan baris ketiga adalah koordinat titik sembarang. Asumsi sumbu x dan y dari semua titik dan juga radius direpresentasikan dengan bilangan bulat.
Keluaran berupa string yang menyatakan posisi titik "Titik di dalam lingkaran 1 dan 2", "Titik di dalam lingkaran 1", "Titik di dalam lingkaran 2", atau "Titik di luar lingkaran 1 dan 2".
Contoh

![Screenshot 2024-10-13 185607](https://github.com/user-attachments/assets/f40ac764-f01e-4d9a-b1c6-dfb7cc0a1294)

![Screenshot 2024-10-13 185635](https://github.com/user-attachments/assets/1f75e804-5bf6-4287-bceb-7490aa613744)

Fungsi untuk menghitung jarak titik (a, b) dan (c, d) dimana rumus jarak adalah:

![Screenshot 2024-10-13 185757](https://github.com/user-attachments/assets/9aa06041-12ec-4a72-bf66-771b9071463b)

dan juga fungsi untuk menentukan posisi sebuah titik sembarang berada di dalam suatu lingkaran atau tidak.

#### Source Code
```go
// Meutya Azzahra Efendi
// 2311102166
// IF-11-06


package main

import (
	"fmt"
	"math"
)

func jarak(a, b, c, d float64) float64 {
	return math.Sqrt(math.Pow(a-c, 2) + math.Pow(b-d, 2))
}

func didalam(cx, cy, r, x, y float64) bool {
	return jarak(cx, cy, x, y) <= r
}

func main() {
	var cx1, cy1, r1, cx2, cy2, r2, x, y float64

	fmt.Println("Masukkan koordinat titik pusat lingkaran 1 (cx, cy) dan radius (r):")
	fmt.Scanln(&cx1, &cy1, &r1)

	fmt.Println("Masukkan koordinat titik pusat lingkaran 2 (cx, cy) dan radius (r):")
	fmt.Scanln(&cx2, &cy2, &r2)

	fmt.Println("Masukkan koordinat titik (x, y):")
	fmt.Scanln(&x, &y)

	if didalam(cx1, cy1, r1, x, y) && didalam(cx2, cy2, r2, x, y) {
		fmt.Println("Titik di dalam lingkaran 1 dan 2")
	} else if didalam(cx1, cy1, r1, x, y) {
		fmt.Println("Titik di dalam lingkaran 1")
	} else if didalam(cx2, cy2, r2, x, y) {
		fmt.Println("Titik di dalam lingkaran 2")
	} else {
		fmt.Println("Titik di luar lingkaran 1 dan 2")
	}
}
```

#### Screenshot Ouput

![Screenshot 2024-10-13 191201](https://github.com/user-attachments/assets/9c078035-8648-4cb6-a369-4aedd3721974)

#### Deskripsi Program

Program Go ini menentukan posisi suatu titik relatif terhadap dua lingkaran.

1. **Fungsi**:
   - `jarak` menghitung jarak antara dua titik.
   - `didalam` memeriksa apakah titik berada di dalam lingkaran.

2. **Input**: Pengguna memasukkan pusat dan radius untuk dua lingkaran, serta koordinat titik.

3. **Output**: Program mencetak apakah titik tersebut berada di dalam kedua lingkaran, salah satu, atau di luar keduanya.

Secara keseluruhan, program ini menggunakan perhitungan jarak untuk mengevaluasi posisi titik terhadap lingkaran.
