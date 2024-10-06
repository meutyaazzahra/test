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
Go hanya mempunyai kata kunci for untuk semua jenis perulangan yang kita pelajari dalam kondisi notasi algoritma. Dua bentuk yang kita gunakan disini adalah struktur while-loop dan repeat-until.
![Screenshot 2024-10-06 180629](https://github.com/user-attachments/assets/9246f2bd-9794-451c-a2e7-a17bdcaf8d3c)
Dalam konsep pemrograman terstruktur, setiap rancangan algoritma harus memenuhi syarat satu pintu masuk dan satu pintu keluar. Karena itu tidaklah diperkenankan untuk membuat program sumber yang mempunyai struktur loop yang mempunyai pintu keluar lebih dari satu, seperti:
- Satu pintu keluar dari kondisi for dan satu lagi dari instruksi if-break
- Atau mempunyai isntruksi if-break yang lebih dari satu
1. Bentuk While-Loop
   Bentuk While-Loop memastikan setiap kali memasuki loop, ada kondisi yang harus terpenuhi (benar/true). Ini juga berarti saat keluar dari loop, maka nilai kondisi tersebut pasti salah/false!
![Screenshot 2024-10-06 181927](https://github.com/user-attachments/assets/3d741a47-88e5-46b8-a426-592b376e5637)
![Screenshot 2024-10-06 182025](https://github.com/user-attachments/assets/2d48f109-8443-4ef8-8ae8-eade308307b0)

3. Bentuk Repeat-Until
   Bentuk repeat-until di perulangan dilakukan terus menerus sampai kondisi keluar terpenuhi. Artinya selama kondisi belum terpenuhi (salah/false) maka perulangan akan terus dilakukan. Pada saat keluar dari loop maka nilai kondisi pasti benar/true!
![Screenshot 2024-10-06 182535](https://github.com/user-attachments/assets/7ac3e011-3004-476d-812b-a6cd1d06698f)
Perhatian: Karena pernyataan kondisi ada di bawah pada bentuk repeat-until, apapun kondisinya, badan loop pasti akan pernah dieksekusi minimum satu kali.
Kode Go di bawah menggunakan algoritma yang sangat mirip dengan algoritma di atas, dengan perbedaan pada digunakannya bentuk while-loop. Umumnya keluaran kedua algoritma sama, kecuali saat maxF diisialisasi dengan nilai 0 atau lebih kecil.
![Screenshot 2024-10-06 183256](https://github.com/user-attachments/assets/9f9fbb25-53f1-4265-ae2e-4e91b9264be1)

## II. GUIDED

# 1. Soal Study Case
Telusuri program berikut dengan cara mengkompilasi dan mengeksekusi program. Silahkan masukkan data yang sesuai sebanyak yang diminta program. Perhatikan keluaran yang diperoleh. Coba terangkan apa sebenarnya yang dilakukan program tersebut?

#### Source Code
```go
package main

import "fmt"

func main() {
	var (
		satu, dua, tiga string
		temp            string
	)
	fmt.Println("Masukan input string: ")
	fmt.Scanln(&satu)
	fmt.Println("Masukan input string: ")
	fmt.Scanln(&dua)
	fmt.Println("Masukan input string: ")
	fmt.Scanln(&tiga)
	fmt.Println("Output awal = " + satu + " " + dua + " " + tiga)
	temp = satu
	satu = dua
	dua = tiga
	tiga = temp
	fmt.Println("Output akhir = " + satu + " " + dua + " " + tiga)
}
```
#### Screenshot Output

![Screenshot 2024-10-06 223353](https://github.com/user-attachments/assets/8f21da29-cf2e-4a09-abcc-a7a9f629a85b)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan tiga string, kemudian mencetak output awal yang menampilkan ketiga string tersebut. Setelah itu, program melakukan pertukaran nilai di antara ketiga string: nilai string pertama menjadi nilai string kedua, nilai string kedua menjadi nilai string ketiga, dan nilai string ketiga menjadi nilai string pertama. Akhirnya, program mencetak output akhir dengan urutan string yang telah dipertukarkan. Program ini menunjukkan dasar-dasar pengolahan input dan output serta penggunaan variabel dalam bahasa Go.

# 2. Soal Study Case
Tahun kabisat adalah tahun yang habis dibagi 400 atau habis dibagi 4 tetapi tidak habis dibagi 100. Buatlah sebuah program yang menerima input sebuah bilangan bulat dan memeriksa apakah bilangan tersebut merupakan tahun kabisat (true) atau bukan (false).
(Contoh input/output, teks bergaris bawah adalah input dari user):

![Screenshot 2024-10-06 194338](https://github.com/user-attachments/assets/bbd85471-8e96-48cc-a54a-0655c4d66031)

#### Source Code
```go
package main

import "fmt"

func main() {
	var tahun int
	fmt.Println("Masukkan sebuah tahun: ")
	fmt.Scanln(&tahun)

	if (tahun%400 == 0) || (tahun%4 == 0 && tahun%100 != 0) {
		fmt.Println(tahun, "adalah tahun kabiat: true")
	} else {
		fmt.Println(tahun, "bukan tahun kabisat: false")
	}
}
```go
package main

import (
	"fmt"
	"math"
)

func main() {
	var jarijari float64
	fmt.Println("Masukkan jari-jari bola: ")
	fmt.Scanln(&jarijari)

	volume := (4.0 / 3.0) * math.Pi * math.Pow(jarijari, 3)
	luas_permukaan := 4 * math.Pi * math.Pow(jarijari, 2)

	fmt.Println("Volume bola dengan jari-jari %.2f adalah %.2f\n", jarijari, volume)
	fmt.Println()
	fmt.Println("luas_permukaan bola dengan jari-jari %.2f adalah %.2f\n", jarijari, luas_permukaan)
}
```
#### Screenshot Output

![Screenshot 2024-10-06 204341](https://github.com/user-attachments/assets/822941e7-3587-40a0-8419-178dd10fbed8)

#### Deskripsi Program
Program Go ini meminta input tahun dari pengguna dan menentukan apakah tahun tersebut adalah tahun kabisat. Jika tahun habis dibagi 400 atau habis dibagi 4 tetapi tidak habis dibagi 100, program mencetak bahwa tahun tersebut adalah tahun kabisat. Jika tidak, program mencetak bahwa tahun tersebut bukan tahun kabisat.

# 3. Soal Study Case
Buat program Bola yang menerima input jari-jari suatu bola (bilangan bulat). Tampilkan volume dan luas kulit bola. volume bola = 4/3 phi r`3 dan luas bola = 4 phi r`2 (phi = 3.14)
(contoh input/output, teks bergaris bawah adalah input dari user):

![Screenshot 2024-10-06 194750](https://github.com/user-attachments/assets/99a44ea0-7fd5-47f3-95d1-5cc430f55dc6)

#### Source Code
```go
package main

import (
        "fmt"
        "math"
)

func main() {
        var jariJari int
        fmt.Print("Jejari = ")
        fmt.Scan(&jariJari)

        // Hitung volume dan luas permukaan
        volume := (4.0 / 3.0) * math.Pi * float64(jariJari*jariJari*jariJari)
        luas := 4 * math.Pi * float64(jariJari*jariJari)

        // Tampilkan hasil
        fmt.Printf("Bola dengan jari-jari %d memiliki volume %.4f dan luas kulit %.4f\n", jariJari, volume, luas)
}
```
#### Screenshot Output

![Screenshot 2024-10-06 205426](https://github.com/user-attachments/assets/882cb3a1-b17e-4899-884a-5a6b6129b5e6)

#### Deskripsi Program
Program Go ini meminta input jari-jari bola dari pengguna, kemudian menghitung dan menampilkan volume serta luas permukaan bola. Volume dihitung dengan rumus \((\frac{4}{3}) \pi r^3\) dan luas permukaan dengan rumus \(4 \pi r^2\). Hasil ditampilkan dengan presisi empat desimal.

## III. Unguided

# 1. Soal Study Case
Dibaca nilai temperatur dalam derajat celcius. Nyatakan temperatur tersebut dalam Fahrenheit
(contoh input/output, teks bergaris bawah adalah input dari user):

![Screenshot 2024-10-06 195141](https://github.com/user-attachments/assets/3e9fff25-9d54-40f9-af6a-61f0e4f96ac8)

Lanjutan program di atas, sehingga temperatur dinyatakan juga dalam derajat reamur dan kelvin.
(contoh input/output, teks bergaris bawah adalah input dari user):

![Screenshot 2024-10-06 195412](https://github.com/user-attachments/assets/89458668-8f60-4726-967b-93e84dad3968)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import "fmt"

func main() {
	var celsius float64

	fmt.Print("Masukkan suhu dalam derajat Celsius: ")
	fmt.Scanln(&celsius)

	fahrenheit := (celsius * 9 / 5) + 32
	reamur := celsius * 4 / 5
	kelvin := celsius + 273.15

	fmt.Printf("Suhu dalam Fahrenheit: %.2f\n", fahrenheit)
	fmt.Printf("Suhu dalam Reamur: %.2f\n", reamur)
	fmt.Printf("Suhu dalam Kelvin: %.2f\n", kelvin)
}
```
#### Screenshot Output

![Screenshot 2024-10-06 210112](https://github.com/user-attachments/assets/73213f02-2c12-4d82-97fa-d65384346d7f)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan suhu dalam derajat Celsius, kemudian mengonversi suhu tersebut ke dalam tiga skala: Fahrenheit, Reamur, dan Kelvin.

# 2. Soal Study Case
Tipe karakter sebenarnya hanya apa yang tampak dalam tampilan. Di dalamnya tersimpan dalam bentuk biner 8 bit (byte) atau 32 bit (rune) saja. Buat program ASCII yang akan membaca 5 buat data integer dan mencetaknya dalam format karakter. Kemudian membaca 3 buah data karakter dan mencetak 3 buah karakter setelah karakter tersebut (menurut tabel ASCII).
Masukkan terdiri dari dua baris. Baris pertama berisi 5 buah data integer. Data integer mempunyai nilai antara 32 s.d. 127. Baris kedua berisi 3 buah karakter yang berdampingan satu dengan yang lain (tanpa dipisahkan spasi).
keluaran juga terdiri dari dua baris. Baris pertama berisi 5 buah representasi karakter dari data yang diberikan, yang berdampingan satu dengan lain, tanpa dipisahkan spasi. Baris kedua berisi 3 buah karakter (juga tidak dipisahkan oleh spasi).

![Screenshot 2024-10-06 200155](https://github.com/user-attachments/assets/86299545-b6da-48b0-98f5-27e863403ffa)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import "fmt"

func main() {
	var numbers [5]int
	var chars [3]byte

	fmt.Println("Masukkan 5 buah data integer (32-127):")
	for i := 0; i < 5; i++ {
		fmt.Scan(&numbers[i])
	}

	fmt.Println("Masukkan 3 buah karakter:")
	for i := 0; i < 3; i++ {
		fmt.Scanf("%c", &chars[i])
	}

	fmt.Print("Karakter dari nilai integer: ")
	for _, num := range numbers {
		fmt.Printf("%c", num)
	}
	fmt.Println()

	fmt.Print("Karakter setelahnya: ")
	for _, char := range chars {
		fmt.Printf("%c", char+1)
	}
	fmt.Println()
}
```
#### Screenshot Output

![Screenshot 2024-10-06 225302](https://github.com/user-attachments/assets/912cf3ef-a24e-4a8a-b8ca-ccc03f85ba7d)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan lima angka integer (dalam rentang 32-127) dan tiga karakter. 
Setelah menerima input, program mencetak karakter yang sesuai dengan nilai integer yang dimasukkan. Selanjutnya, program juga mencetak karakter yang dimasukkan, tetapi dengan nilai ASCII yang ditambahkan satu. Dengan demikian, karakter yang dihasilkan adalah hasil dari penambahan satu pada setiap karakter yang dimasukkan.

# 3. Soal Study Case
Siswa kelas IPA di salah satu sekolah menengah atas di Indonesia sedang mengadakan praktikum kimia. Di setiap percobaan akan menggunakan 4 tabung reaksi, yang mana susunan warna cairan disetiap tabung akan menentukan hasil percobaan. Siswa diminta untuk mencatat hasil percobaan tersebut. Percobaan dikatakan berhasil apabila susunan warna zar cair pada gelas 1 hingga gelas 4 secara berurutan adalah 'merah', 'kuning', 'hijau', dan 'ungu' selama 5 kali percobaan berulang.
Buatlah sebuah program yang menerima yang menerima input berupa warna dari ke 4 gelas reaksi sebanyak 5 kali percobaan. Kemudian program akan menampilkan true apabila urutan warna sesuai dengan informasi yang diberikan pada paragraf sebelumnya dan false untuk urutan warna lainnya. 
Perhatikan contoh sesi interaksi program seperti dibawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 200838](https://github.com/user-attachments/assets/f9794afe-1222-45a3-a73d-5dad241097de)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import (
	"bufio"
	"fmt"
	"os"
	"strings"
)

func main() {
	// Urutan warna yang benar
	correctOrder := []string{"merah", "kuning", "hijau", "ungu"}

	// Membaca input untuk 5 percobaan
	reader := bufio.NewReader(os.Stdin)
	var hadError bool

	for i := 1; i <= 5; i++ {
		fmt.Printf("Percobaan %d: ", i)

		// Membaca input dari pengguna
		input, _ := reader.ReadString('\n')
		input = strings.TrimSpace(input)

		// Memisahkan input berdasarkan spasi
		colors := strings.Split(input, " ")

		// Mengecek apakah urutan warna sesuai
		for j := 0; j < 4; j++ {
			if colors[j] != correctOrder[j] {
				hadError = true
				break
			}
		}
	}

	// Menampilkan hasil
	if !hadError {
		fmt.Println("BERHASIL: true")
	} else {
		fmt.Println("BERHASIL: false")
	}
}
```
#### Screenshot Output

![Screenshot 2024-10-06 213046](https://github.com/user-attachments/assets/89e5463b-ca65-4f2a-bc9a-2fa61f7ca8a5)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan urutan warna dalam lima percobaan. Warna yang benar adalah "merah", "kuning", "hijau", dan "ungu". 
Setelah setiap input, program memeriksa apakah urutan warna sesuai dengan yang benar. Jika semua percobaan sesuai, program mencetak "BERHASIL: true"; jika tidak, program mencetak "BERHASIL: false".

# 4. Soal Study Case
Suatu pita (string) berisi kumpulan nama-nama bunga yang dipisahkan oleh spasi dan '-', contoh pita diilustrasikan seperti berikut ini.
Pita: mawar-melati-tulip-teratai-kamboja-anggrek
Buatlah sebuah program yang menerima input sebuah bilangan bulat positif dan tidak nol N, kemudian program akan meminta input berupa nama bunga secara berulang sebanyak N kali dan nama tersebut disimpan ke dalam pita.
(petunjuk: gunakan operasi penggabungan string dengan operator "+")
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 201331](https://github.com/user-attachments/assets/db0ec3b7-9879-4dff-aac0-ba76313c2a8a)

Modifikasi program sebelumnya, proses input akan berhenti apabila user mengetikkan "SELESAI". Kemudian tampilan isi pita beserta banyaknya bunga yang ada di dalam pita.
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 201523](https://github.com/user-attachments/assets/3f701357-a41e-47a7-8621-396faa43d448)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import (
	"bufio"
	"fmt"
	"os"
	"strings"
)

func main() {
	// Variabel pita digunakan untuk menyimpan daftar nama bunga
	var pita string
	var TotalBunga int

	// Menggunakan scanner untuk membaca input dari pengguna
	scanner := bufio.NewScanner(os.Stdin)

	fmt.Print("Masukkan nama bunga dan ketik 'SELESAI' untuk mengakhiri. :\n")

	for {
		TotalBunga++
		fmt.Printf("Bunga %d: ", TotalBunga)

		// Membaca input dari pengguna
		scanner.Scan()
		input := scanner.Text()

		// Cek jika pengguna mengetikkan "SELESAI" maka program akan berhenti
		if strings.ToUpper(input) == "SELESAI" {
			TotalBunga-- // Mengurangi jumlah bunga karena input "SELESAI" tidak dihitung
			break
		}

		// Menambahkan nama bunga ke pita 
		if pita == "" {
			pita = input
		} else {
			pita += " - " + input
		}
	}

	// Menampilkan hasil akhir pita dan jumlah bunga yang dimasukkan
	fmt.Println("Pita:", pita)
	fmt.Println("Total bunga:", TotalBunga )
}
```
#### Screenshot Output

![Screenshot 2024-10-06 214730](https://github.com/user-attachments/assets/1ce5b35f-eb4f-4f50-98a0-23464df9472c)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan nama-nama bunga secara berurutan hingga mereka mengetik "SELESAI" untuk mengakhiri input. 
Setiap nama bunga yang dimasukkan disimpan dalam variabel `pita`, dan jumlah total bunga yang dimasukkan dihitung. Setelah input selesai, program menampilkan daftar nama bunga yang dimasukkan dan total jumlah bunga.

# 5. Soal Study Case
Setiap hari Pak Andi membawa bayak barang belanjaan dari pasar dengan mengendarai sepeda motor. Barang belanjaan tersebut dibawa dalam kantong terpal di kiri-kanan motor. Sepeda motor tidak akan oleng jika selisih berat barang di kedua kantong sisi tidak lebih dari 9 kg.
Buatlah program Pak Andi yang menerima input dua buah bilangan real positif yang menyatakan berat total masing-masing isi kantong terpal. Program akan terus meminta input bilangan tersebut hingga salah satu kantong terpal berisi 9 kg atau lebih.
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 202136](https://github.com/user-attachments/assets/faae7476-1b49-4a17-8209-15a5776f0dc8)

Pada modifikasi program tersebut, program akan menampilkan true jika selisih kedua isi kantong lebih dari atau sama dengan 9 kg. Program berhenti memproses apabila total berat isi kedua kantong melebihi 150 kg atau salah satu kantong beratnya negatif.
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 202351](https://github.com/user-attachments/assets/013bd445-cd40-4cb4-895c-e36a54f9f0bc)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import "fmt"

func main() {
	for {
		var berat1, berat2 float64

		fmt.Print("Masukkan berat belanjaan di kedua kantong: ")
		_, err := fmt.Scan(&berat1, &berat2)
		if err != nil {
			fmt.Println("Input tidak valid.")
			return
		}

		if berat1+berat2 > 150 || berat1 < 0 || berat2 < 0 {
			fmt.Println("Proses selesai.")
			break
		}

		selisih := berat1 - berat2
		if selisih < 0 {
			selisih = -selisih
		}
		akanOleng := selisih >= 9

		fmt.Printf("Sepeda motor pak Andi akan oleng: %t\n",akanOleng)
	}
}
```
#### Screenshot Output

![Screenshot 2024-10-06 215319](https://github.com/user-attachments/assets/ef1370ed-056f-4926-9461-4b2ec7d3b79e)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan berat belanjaan dalam dua kantong secara berulang. 
Jika total berat melebihi 150 kg atau ada berat negatif, program akan menghentikan proses. Jika tidak, program menghitung selisih berat antara kedua kantong dan menentukan apakah sepeda motor pak Andi akan oleng berdasarkan selisih tersebut (jika selisih ≥ 9 kg). Hasilnya ditampilkan sebagai boolean.

# 6. Soal Study Case
Diberikan sebuah persamaan sebagai berikut

![Screenshot 2024-10-06 202508](https://github.com/user-attachments/assets/4200441c-af3e-4e9e-9751-4ec75cb1ec49)

Buatlah sebuah program yang menerima input sebuah bilangan sebagai K, kemudian menghitung dan menampilkan nilai f(K) sesuai persamaa di atas.
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 202710](https://github.com/user-attachments/assets/238e9c84-144d-4dd2-a5d8-1caf9cde5f50)

√2 merupakan bilangan irasional. Meskipun demikian, nilai tersebut dapat dihampiri dengan rumus berikut:

![Screenshot 2024-10-06 202838](https://github.com/user-attachments/assets/bd04ec05-84db-4d91-b6af-f26a298d031d)

Modifikasi program sebelumnya yang menerima input integer K dan menghitung √2 untuk K tersebut. Hampiran √2 dituliskan dalam ketelitian 10 angka di belakang koma.  
Perhatikan contoh sesi interaksi program seperti di bawah ini (teks bergaris bawah adalah input/read):

![Screenshot 2024-10-06 203037](https://github.com/user-attachments/assets/f7362a96-fc04-4ec1-9465-241632320ac9)

#### Source Code
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import (
	"fmt"
	"math"
)

func main() {
	var k float64

	fmt.Print("Masukkan nilai K: ")
	fmt.Scan(&k)

	fk := math.Pow(4*k+2, 2) / ((4*k + 1) * (4*k + 3))

	fmt.Printf("Nilai f(k) = %.10f\n",fk)
}
```
#### setelah dimodifikasi
```go
// Meutya Azzahra Efendi
// IF-11-06
// 2311102166
package main

import (
	"fmt"
	"math"
)

func main() {
	var k int

	for {
		fmt.Print("Masukkan nilai K: ")
		_, err := fmt.Scan(&k)
		if err != nil {
			fmt.Println("Input tidak valid.")
			return
		}

		if k < 0 {
			fmt.Println("Nilai K harus positif.")
			continue
		}

		akarDua := 0.0
		for i := 0; i <= k; i++ {
			pembilang := math.Pow(4*float64(i)+2, 2)
			penyebut := (4*float64(i) + 1) * (4*float64(i) + 3)
			akarDua += pembilang / penyebut
		}

		fmt.Printf("Nilai akar 2 = %.10f\n",akarDua)
	}
}
```
#### Screenshot Output

![Screenshot 2024-10-06 222602](https://github.com/user-attachments/assets/d1bfc51b-f7e3-407f-a35a-3f0cced36aba)

setelah dimodifikasi

![Screenshot 2024-10-06 222658](https://github.com/user-attachments/assets/83269fa3-d44c-42b6-ae83-1da5e338c064)

#### Deskripsi Program
Program Go ini meminta pengguna untuk memasukkan nilai `K`, kemudian menghitung nilai `f(k)` menggunakan rumus matematika yang ditentukan. Hasil perhitungan ditampilkan dengan presisi 10 desimal. Program ini berfungsi untuk melakukan evaluasi fungsi matematika berdasarkan input yang diberikan.

setelah dimodifikasi
Program Go ini meminta pengguna untuk memasukkan nilai `K` dan menghitung nilai perkiraan akar dua berdasarkan rumus tertentu. Program melakukan validasi untuk memastikan `K` adalah angka positif. Selama loop, program menghitung nilai berdasarkan rumus yang melibatkan penjumlahan pecahan hingga `K` dan menampilkan hasilnya dengan presisi 10 desimal. Program ini terus meminta input hingga pengguna memilih untuk menghentikannya.
