# Modul 16: Skema Pemrosesan Sekuensial (Pengayaan)

Modul 16 merupakan modul pengayaan tingkat lanjut yang membahas pola perancangan algoritma untuk memproses serangkaian data (data stream / sequence). Pola-pola ini merupakan fondasi penting dalam pemrosesan file, parsing data jaringan, dan manipulasi struktur data berukuran besar.

---

## 1. Analogi Konsep: Mesin Pemindai Paket di Ban Berjalan

Bayangkan sebuah mesin pemindai barcode otomatis pada ban berjalan di pusat logistik:
- Barang datang satu demi satu secara berurutan (sekuensial).
- Mesin membaca barcode barang pertama.
- Selama barang yang lewat bukan tanda penutup kontainer (**Marker / Sentinel**, misal kode `SELESAI`):
  1. Catat berat barang.
  2. Tambahkan ke akumulator total muatan.
  3. Pindai barang berikutnya di ban berjalan.
- Begitu barcode `SELESAI` terbaca, mesin langsung berhenti dan mencetak manifesto pengiriman.

![Skema Pemrosesan Sekuensial](../assets/images/sequential-stream.svg)

### Simulasi Animasi Pemrosesan Sekuensial dengan Marker
Berikut animasi aliran data stream yang terus diakumulasi hingga pembacaan marker menghentikan loop:

![Animasi Stream Sekuensial](../assets/images/sequential-stream-animation.gif)

---

## 2. Empat Pola Pemrosesan Sekuensial Standar

```mermaid
flowchart TD
    subgraph Pola1 [Pola 1: Tanpa Marker - Jumlah Data Diketahui di Awal]
        A1[Baca Jumlah N] --> A2[Loop Sebanyak N Kali]
        A2 --> A3[Proses Tiap Data Masukan]
    end

    subgraph Pola2 [Pola 2: Dengan Marker - Berhenti pada Nilai Tertentu]
        B1[Baca Data Pertama E] --> B2{E == MARKER ?}
        B2 -->|Tidak| B3[Proses E]
        B3 --> B4[Baca Data Berikutnya E]
        B4 --> B2
        B2 -->|Ya| B5[Selesai]
    end

    subgraph Pola3 [Pola 3: Kemungkinan Data Kosong]
        C1[Pemeriksaan langsung pada data pertama jika langsung bernilai marker]
    end

    subgraph Pola4 [Pola 4: Elemen Pertama Khusus]
        D1[Inisialisasi Nilai Min/Max dari Elemen Pertama Sebelum Loop]
    end
```

---

## 3. Implementasi Pola: Mencari Nilai Maksimum dan Rata-rata

Pada kasus mencari nilai maksimum atau minimum, sangat dianjurkan untuk membaca elemen pertama terlebih dahulu sebagai patokan awal sebelum memasuki loop pemrosesan data berikutnya:

```go
package main

import "fmt"

func main() {
    var x int
    const MARKER = -999

    fmt.Scan(&x)
    if x == MARKER {
        fmt.Println("Rangkaian data kosong!")
        return
    }

    max := x
    total := 0
    banyakData := 0

    for x != MARKER {
        if x > max {
            max = x
        }
        total += x
        banyakData++

        // Baca elemen berikutnya
        fmt.Scan(&x)
    }

    rataRata := float64(total) / float64(banyakData)
    fmt.Println("Banyak Data :", banyakData)
    fmt.Println("Nilai Tertinggi:", max)
    fmt.Printf("Rata-rata   : %.2f\n", rataRata)
}
```

---

## 4. Soal Latihan & Skeleton Code

### Soal 1: Pencari Nilai Minimum Rangkaian Angka
Buatlah program yang membaca serangkaian bilangan bulat positif yang diakhiri oleh angka `-1` sebagai marker. Tentukan dan cetak nilai terkecil (minimum) dari angka-angka yang dimasukkan. Jika masukan langsung `-1`, cetak "Data Kosong".

#### Skeleton Code:
```go
package main

import "fmt"

func main() {
    var bilangan int
    const MARKER = -1

    fmt.Scan(&bilangan)
    if bilangan == MARKER {
        fmt.Println("Data Kosong")
        return
    }

    min := bilangan
    // TODO: Gunakan for bilangan != MARKER
    // Di dalam loop:
    // 1. Jika bilangan < min, maka min = bilangan
    // 2. Baca bilangan berikutnya: fmt.Scan(&bilangan)

    fmt.Println("Nilai Terkecil:", min)
}
```

### Soal 2: Penghitung Kata dengan Karakter Titik (.)
Buatlah program yang membaca karakter per karakter hingga ditemukan karakter titik (`.`). Hitung berapa kali karakter vokal (`a`, `i`, `u`, `e`, `o`) muncul di dalam rangkaian teks tersebut.

#### Skeleton Code:
```go
package main

import "fmt"

func main() {
    var c byte
    vokalCount := 0

    for {
        fmt.Scanf("%c", &c)
        if c == '.' {
            break
        }

        // TODO: Jika c adalah 'a', 'i', 'u', 'e', 'o' (huruf kecil maupun kapital)
        // Tambahkan vokalCount++
    }

    fmt.Println("Banyak Karakter Vokal:", vokalCount)
}
```
