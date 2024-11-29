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
# Source Code
# Screenshot Output
# Deskripsi Program

# 2. Soal study Case
# Source Code
# Screenshot Output
# Deskripsi Program

### III. UNGUIDED

# 1. Soal study Case
# Source Code
# Screenshot Output
# Deskripsi Program

# 2. Soal study Case
# Source Code
# Screenshot Output
# Deskripsi Program

# 3. Soal study Case
# Source Code
# Screenshot Output
# Deskripsi Program
