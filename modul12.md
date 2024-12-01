<h1 align="center">LAPORAN PRAKTIKUM</h1>
<h2 align="center">ALGORITMA DAN PEMROGRAMAN 2</h2>

<h3 align="center">MODUL 12</h3>
<h4 align="center">PENGURUTAN DATA</h4>

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

### 12.1 Ide Algoritma Selection Sort
Pengurutan secara seleksi ini idenya adalah mencari nilai ekstrim pada sekumpulan data, kemudian meletakkan pada posisi yang seharusnya. Pada penjelasan berikut ini data akan diurut membesar (ascending) dan data dengan indeks terkecil ada di "kiri" dan indeks besar ada di "kanan".
1) Cari nilai terkecil di dalam rentang data tersisa
2) Pindahkan/tukar tempat dengan data yang berada pada posisi paling kiri pada rentang data tersisa tersebut
3) Ulangi proses ini sampai tersisa hanya satu data saja
Algoritma ini dikenal juga dengan nama Selection Sort, yang mana pada algoritma ini melibatkan dua proses yaitu pencarian indeks nilai ekstrim dan proses pertukaran dua nilai atau swap.

| No | Notasi Algoritma                                 | Notasi dalam bahasa Go |
|----|------------------------------------------------|-----------------------|
| 1  | i ← 1                                           | i = 1                  |
| 2  | while i <= n-1 do                               | for i <= n-1 {          |
| 3  |     idx_min ← i-1                               |     idx_min = i - 1     |
| 4  |     j ← i                                      |     for j < n {         |
| 5  |     while j < n do                              |         if a[idx_min] > a[j] { |
| 6  |         if a[idx_min] > a[j] then                |             idx_min = j   |
| 7  |             idx_min ← j                        |         }                |
| 8  |         endif                                  |     }                  |
| 9  |         j ← j + 1                              |     j = j + 1          |
| 10 |     endwhile                                  |     }                  |
| 11 |     t ← a[idx_min]                              |     t = a[idx_min]      |
| 12 |     a[idx_min] ← a[i-1]                          |     a[idx_min] = a[i-1] |
| 13 |     a[i-1] ← t                                  |     a[i-1] = t          |
| 14 |     i ← i + 1                                  |     i = i + 1          |
| 15 | endwhile                                      | }                     |

### 12.2 Algoritma Selection Sort
Adapun algoritma selection sor pada untuk mengurutkan array bertipe data bilangan bulat secara membesar atau ascendin adalah sebagai berikut.

```go
type arrInt [4321]int

func selectionSort(T *arrInt, n int) {
    /* I.S. terdefinisi array T yang berisi n bilangan bulat
       F.S. array T terurut secara ascending atau membesar dengan SELECTION SORT */

    var t, i, j, idx_min int

    for i <= n-1 {
        idx_min = i - 1
        for j < n {
            if T[idx_min] > T[j] {
                idx_min = j
            }
            j = j + 1
        }
        t = T[idx_min]
        T[idx_min] = T[i-1]
        T[i-1] = t
        i = i + 1
    }
}
```
Sama halnya apabila array yang akan diurutkan adalah bertipe data struct, maka tambahkan field pada saat proses perbandingan nilai ekstrim, kemudian tipe data dari variabel t sama dengan struct dari arraynya.

```go
type mahasiswa struct {
    nama, nim, kelas, jurusan string
    ipk float64
}

type arrMhs [2023]mahasiswa

func selectionSort2(T *arrMhs, n int) {
    /* I.S. terdefinisi array T yang berisi n data mahasiswa
       F.S. array T terurut secara ascending atau membesar berdasarkan ipk dengan
       menggunakan algoritma SELECTION SORT */

    var t mahasiswa
    var i, j, idx_min int

    for i <= n-1 {
        idx_min = i - 1
        for j < n {
            if T[idx_min].ipk > T[j].ipk {
                idx_min = j
            }
            j = j + 1
        }
        t = T[idx_min]
        T[idx_min] = T[i-1]
        T[i-1] = t
        i = i + 1
    }
}
```

### 12.3 Ide Algoritma Isertion Sort
Pengurutan secara Insertion ini idenya adalah menyisipkan suatu nilai pada posisi yang seharusnya. Berbeda dengan pengurutan seleksi, yang mana pada pengurutan ini tidak dilakukan pencarian nilai ekstrim terlebih dahulu, cukup memilih suatu nilai tertentu kemudian mencari posisinya secara sequential search. Pada penjelasan berikut ini data akan diurut mengecil (descending) dan data dengan indeks terkecil ada di "kiri" dan indeks besar ada di "kanan".
1) Untuk satu data yang belum terurut daru sejumlah data yang sudah diurutkan:
   Geser data yang sudah terurut tersebut (ke kanan), sehingga ada satu ruang kosong untuk memasukkan data yang belum terurut ke dalam data yang sudah terurut dan tetap menjaga keterurutan.
2) Ulangi proses tersebut untuk setiap data yang belum terurut terhadaap rangkaian data yang sudah terurut

Algortima ini dikenal juga dengan nama Insertion Sort, yang mana pada algoritma ini melibatkan dua proses yaitu pencarian skuensial dan penyisipan.

| No | Notasi Algoritma                                 | Notasi dalam bahasa Go |
|----|------------------------------------------------|-----------------------|
| 1  | i ← 1                                           | i = 1                  |
| 2  | while i <= n-1 do                               | for i <= n-1 {          |
| 3  |     j ← i                                      |     j = i              |
| 4  |     temp ← a[j]                                 |     temp = a[j]        |
| 5  |     while j > 0 and temp > a[j-1] do             |     for j > 0 && temp > a[j-1] { |
| 6  |         a[j] ← a[j-1]                           |         a[j] = a[j-1]   |
| 7  |         j ← j - 1                              |         j = j - 1       |
| 8  |     endwhile                                  |     }                  |
| 9  |     a[j] ← temp                                 |     a[j] = temp        |
| 10 |     i ← i + 1                                  |     i = i + 1          |
| 11 | endwhile                                      | }                     |

### 12.4 Algoritma Insertion Sort
Adapun algoritma Insertion Sort pada untuk mengurutkan array bertipe data bilangan bulat secara mengecil atau descending adalah sebagai berikut ini.

```go
type arrInt [4321]int

func insertionSort1(T *arrInt, n int) {
    /* I.S. terdefinisi array T yang berisi n bilangan bulat
       F.S. array T terurut secara mengecil atau descending dengan INSERTION SORT */

    var temp, i, j int

    for i <= n-1 {
        j = i
        temp = T[j]
        for j > 0 && temp > T[j-1] {
            T[j] = T[j-1]
            j = j - 1
        }
        T[j] = temp
        i = i + 1
    }
}
```

Sama halnya apabila array yang akan diurutkan adalah bertipe data struct, maka tambahkan field pada saat proses perbandingan dalam pencarian posisi, kemudian tipe data dari variabel temp sama dengan struct dari arraynya.

```go
type mahasiswa struct {
    nama, nim, kelas, jurusan string
    ipk float64
}

type arrMhs [2023]mahasiswa

func insertionSort2(T *arrMhs, n int) {
    /* I.S. terdefinisi array T yang berisi n data mahasiswa
       F.S. array T terurut secara mengecil atau descending berdasarkan nama dengan
       menggunakan algoritma INSERTION SORT */

    var temp mahasiswa
    var i, j int

    for i <= n-1 {
        j = i
        temp = T[j]
        for j > 0 && temp.nama > T[j-1].nama {
            T[j] = T[j-1]
            j = j - 1
        }
        T[j] = temp
        i = i + 1
    }
}
```

### II. GUIDED

# 1. Soal study Case

Hercules, preman terkenal seantero Ibukota, memiliki kerabat di banyak daerah. Tentunya Hercules sangat suka mengunjungi semua kerabatnya itu. Diberikan masukan nomor rumah dari semua kerabatnya di suatu daerah, buatlah program rumahkebarabt yang akan menyusun nomor-nomor rumah kerabatnya secara terurut membesar menggunakan algortma selection sort.
Masukan dimulai dengan sebuah integer n (0 < n < 1000), banyaknya daerah kerabat Hercules tinggal. Isi n baris berikutnya selalu dimulai dengan sebuah integer m (0 < m < 1000000) yang menyatakan banyaknya rumah kerabat di daerah tersebut, diikuti dengan rangkaian bilangan bulat positif, nomor rumah para kerabat.
Keluaran terdiri dari n baris, yaitu rangkaian rumah kerabatnya terurut membesar di masing-masing daerah.

| No | Masukan | Keluaran |
|---|---|---|
| 1  | 3        | 1 2 7 9 13 |
|   | 5 2 1 7 9 13 | 15 27 39 75 133 189 |
| 6  | 189 15 27 39 75 133 | 1 4 9 |
|   | 3 4 9 1 |  |

Keterangan: Terdepat 3 daerah dalam contoh input dan di masing-masing daerah mempunyai 5, 6, dan 3 kerabat.

# Source Code

```go
package main

import (
	"fmt"
)

// Fungsi untuk mengurutkan array menggunakan Selection Sort
func selectionSort(arr []int, n int) {
	for i := 0; i < n-1; i++ {
		idxMin := i
		for j := i + 1; j < n; j++ {
			// Cari elemen terkecil
			if arr[j] < arr[idxMin] {
				idxMin = j
			}
		}
		// Tukar elemen terkecil dengan elemen di posisi i
		arr[i], arr[idxMin] = arr[idxMin], arr[i]
	}
}

func main() {
	var n int
	fmt.Print("Masukkan jumlah daerah kerabat (n): ")
	fmt.Scan(&n)

	// Proses tiap daerah
	for daerah := 1; daerah <= n; daerah++ {
		var m int
		fmt.Printf("\nMasukkan jumlah nomor rumah kerabat untuk daerah %d: ", daerah)
		fmt.Scan(&m)

		// Membaca nomor rumah untuk daerah ini
		arr := make([]int, m)
		fmt.Printf("Masukkan %d nomor rumah kerabat: ", m)
		for i := 0; i < m; i++ {
			fmt.Scan(&arr[i])
		}

		// Urutkan array dari terkecil ke terbesar
		selectionSort(arr, m)

		// Tampilkan hasil
		fmt.Printf("Nomor rumah terurut untuk daerah %d: ", daerah)
		for _, num := range arr {
			fmt.Printf("%d ", num)
		}
		fmt.Println()
	}
}
```

# Screenshot Output

![image](https://github.com/user-attachments/assets/530b26a0-c0d4-4fe2-99ed-c94c8ced01b1)

# Deskripsi Program

# 2. Soal study Case

Buatlah sebuah program yang digunakan untuk membaca data integer seperti contoh yang diberikan dibawah ini, kemudian diurutkan (menggunakan metode insertion sort) dan memeriksa apakah data yang terurut berjarak sama terhadap data sebelumnya.
Masukan terdiri dari sekumpulan bilangan buat yang diakhiri oleh bilangan negatif. Hanya bilangan non negatif saja yang disimpan ke dalam array.
Keluaran terdiri dari dua baris. Baris pertam adalag isi dari array setelah dilakukan pengurutan, sedangkan baris kedua adalah status jarak setiap bilangan yang ada di dalam array. "Data berjarak x" atau "Data berjarak tidak tetap".
Contoh masukan dan keluaran

| No | Masukan                                  | Keluaran                               |
|---|---|---|
| 1  | 31 13 25 43 1 7 19 37 -5                 | 1 7 13 19 25 31 37 43 <br> Data berjarak 6 |
| 2  | 4 48 14 8 26 1 38 32 2 -31                | 1 2 4 8 14 26 32 38 40 <br> Data berjarak tidak tetap |

# Source Code

```go
package main

import (
	"fmt"
)

// Fungsi untuk mengurutkan array menggunakan Insertion Sort
func insertionSort(arr []int, n int) {
	for i := 1; i < n; i++ {
		key := arr[i]
		j := i - 1

		// Geser elemen yang lebih besar dari key ke kanan
		for j >= 0 && arr[j] > key {
			arr[j+1] = arr[j]
			j--
		}
		arr[j+1] = key
	}
}

// Fungsi untuk memeriksa apakah selisih elemen array tetap
func isConstantDifference(arr []int, n int) (bool, int) {
	if n < 2 {
		return true, 0
	}

	difference := arr[1] - arr[0]
	for i := 1; i < n-1; i++ {
		if arr[i+1]-arr[i] != difference {
			return false, 0
		}
	}
	return true, difference
}

func main() {
	var arr []int
	var num int

	// Input data hingga bilangan negatif ditemukan
	fmt.Println("Masukkan data integer (akhiri dengan bilangan negatif):")
	for {
		fmt.Scan(&num)
		if num < 0 {
			break
		}
		arr = append(arr, num)
	}

	n := len(arr)

	// Urutkan array menggunakan Insertion Sort
	insertionSort(arr, n)

	// Periksa apakah selisih elemen tetap
	isConstant, difference := isConstantDifference(arr, n)

	// Tampilkan hasil pengurutan
	fmt.Println("Array setelah diurutkan:")
	for _, val := range arr {
		fmt.Printf("%d ", val)
	}
	fmt.Println()

	// Tampilkan status jarak
	if isConstant {
		fmt.Printf("Data berjarak %d\n", difference)
	} else {
		fmt.Println("Data berjarak tidak tetap")
	}
}
```

# Screenshot Output

![image](https://github.com/user-attachments/assets/16aea267-4dcb-48e8-bf0c-6c7050fcca2b)

# Deskripsi Program

### III. UNGUIDED

# 1. Soal study Case

Belakang diketahui ternyata Hercules itu tidak berani menyebrang jalan, maka selalu diusahan agar hanya menyebrang jalan sesedikit mungkin, hanya diujung jalan. Karena nomor rumah sisi kiri jalan selalu ganjil dan sisi kanan jalan selalu genap, maka buatlah program kerabat dekat yang akan menampilkan nomor rumah mulai dari nomor yang ganjil lebih dulu terurut membesar dan kemudian menampilkan nomor rumah dengan nomor genap terurut mengecil.
Formal Masukan masih persis sama seperti sebelumnya
Keluaran terdiri dari n baris yaitu rangkaian rumah kerabatnya terurut membesar untuk nomor ganjil, diikuti dengan terurut mengecil untuk nomor genap, di masing-masing daerah.

| No | Masukan | Keluaran |
|---|---|---|
| 1  | 3        | 1 13 12 8 2 |
|   | 5 2 1 7 9 13 | 15 27 39 75 133 189 |
| 6  | 189 15 27 39 75 133 | 8 4 2 |
|   | 3 4 9 1 |  |

Keterangan: Terdapat 3 daerah dalam contoh masukan. Baris kedua berisi campuran bilangan ganjil dan genap. Baris berikutnya hanya berisi bilangan ganjil dan baris terakhir hanya berisi bilangan genap.
Petunjuk:
- Waktu pembacaan data, bilangan ganjil dan genap dipisahkan ke dalam dua array yang berbeda, untuk kemudian masing-masing diurutkan tersendiri.
- Atau, tetap disimpan dalam satu array, diurutkan secara keseluruhan. Tetapi pada waktu pencetakan, mulai dengan mencetak semua nilai ganjil lebih dulu, kemudian setelah selesaii cetaklah semua nilai genapnya.

# Source Code
# Screenshot Output
# Deskripsi Program

# 2. Soal study Case

Kompetisi pemrograman yang baru saja berlalu diikuti oleh 17 tim dari berbagai perguruan tinggi ternama. Dalam kompetisi tersebut, setiap tim berlomba untuk menyelesaikan sebanyak mungkin problem yang diberikan. Dari 13 problem yang diberikam, ada satu problem yang menarik. Problem tersebut mudah dipahami, hampir semua tim mencoba untuk menyelesaikannya, tetapi hanya 3 tim yang berhasil. Apa sih problemnya?
"Median adalah nilai tengah dari suatu koleksi data yang sudah terurut. Jika jumlah data genap, maka nilai median adalah rerata dari kedua nilai tengahnya. Pada problem ini, semua data merupakan bilangan bulat positif dan karenanya rerata nilai tengah dibulatkan ke bawah."
Buatlah program median yang mencetak nilai median terhadap seluruh data yang sudah terbaca, jika data yang dibaca saat itu adalah 0.
Masukan berbentuk rangkaian bilangan bulat. Masukan tidak akan berisi lebih dari 1000000 data, tidak termasuk bilangan 0. Data 0 merupakan tanda bahwa median harus dicetak, tidak termasuk data yang dicari mediannya. Data masukan diakhiri dengan bilangan bulat -5313.
Keluaran adalah median yang diminta, satu data perbaris.

| No | Masukan                                  | Keluaran |
|---|---|---|
| 1  | 7 23 11 8 5 19 2 29 3 13 17 8 -5813       | 11       |
|    |                                        | 12       |

Keterangan:
Sampai bilangan 0 yang pertama, data terbaca adalah 7 23 11 setelah tersusun: 7 11 23 maka median saat itu adalah 11.
Sampai bilangan 0 yang kedua, data adalah 7 23 11 5 19 2 29 3 13 17, setelah tersusun diperoleh: 2 3 5 7 11 13 17 19 23 29. Karena ada 10 data, genap, maka median adalah (11+12)/2=12
Petunjuk:
untuk setiap data bukan 0 (dan bukan marker -5313541) simpan ke dalam array dan setiap kali menemukan bilangan 0, urutkanlah data yang sudah tersimpan dengan menggunakan metode insertion sort dan ambil mediannya.

# Source Code
# Screenshot Output
# Deskripsi Program

# 3. Soal study Case

Sebuah perpustakaan digunakan untuk mengelola data buku di dalam suatu perpustakaan. Misalnhya terdefinisi struct dan array seperti berikut ini:
```go
const nMax : integer = 7919
type Buku = <
    id, judul, penulis, penerbit : string
    eksemplar, tahun, rating : integer
>
type DaftarBuku = array [1..nMax] of Buku
Pustaka : DaftarBuku
nPustaka : integer
```
Masukan terdiri dari beberapa baris. Baris pertama adalah bilangan bulat N yang menyatakan banyaknya data buku yang ada di dalam perpustakaan. N baris berikutnya, masing-masingnya adalah data buku sesuai dengan atribut atau field pada struct. Baris terakhir adalah bilangan bulat yang menyatakan rating buku yang akan dicari.
Keluaran terdiri dari beberapa baris. Baris pertama adalah data buku terfavorit, baris kedua adalah lima judul buku dengan rating tinggi, selanjutnya baris terakhir adalah data buku yang dicari sesuai rating yang diberikan pada masukan baris terakhir.
Lengkapi subprogram-subprogram dibawah ini, sesuai dengan I.S dan F.S yang diberikan.
```pascal
procedure DaftarkanBuku(in/out pustaka: DaftarBuku; n: integer);
{ I.S. sejumlah n data buku telah siap para piranti masukan
  F.S. n berisi sebuah nilai, dan pustaka berisi sejumlah n data buku }

procedure CetakTerfavorit(in pustaka: DaftarBuku; n: integer);
{ I.S. array pustaka berisi n buah data buku dan belum terurut
  F.S. Tampilan data buku (judul, penulis, penerbit, tahun)
        terfavorit, yaitu memiliki rating tertinggi }

procedure UrutBuku(in/out pustaka: DaftarBuku; n: integer);
{ I.S. Array pustaka berisi n data buku
  F.S. Array pustaka terurut menurun/mengecil terhadap rating.
        Catatan: Gunakan metoda Insertion sort }

procedure Cetak5Terbaru(in pustaka: DaftarBuku; n: integer);
{ I.S. pustaka berisi n data buku yang sudah terurut menurut rating
  F.S. Laporan 5 judul buku dengan rating tertinggi
        Catatan: Isi pustaka mungkin saja kurang dari 5 }

procedure CariBuku(in pustaka: DaftarBuku; n: integer; r: integer);
{ I.S. pustaka berisi n data buku yang sudah terurut menurut rating
  F.S. Laporan salah satu buku (judul, penulis, penerbit, tahun,
        eksemplar, rating) dengan rating yang diberikan. Jika tidak ada buku
        dengan rating yang ditanyakan, cukup tuliskan "Tidak ada buku dengan
        rating seperti itu". Catatan: Gunakan pencarian biner/belah dua. }
```
# Source Code
# Screenshot Output
# Deskripsi Program