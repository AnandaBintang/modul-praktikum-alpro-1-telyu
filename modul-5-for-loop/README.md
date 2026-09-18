# Modul 5: Struktur Kontrol For-Loop

Modul 5 membahas paradigma perulangan (looping) menggunakan instruksi `for` berbasis pencacah (counter). Perulangan memungkinkan komputer mengeksekusi instruksi yang sama berkali-kali tanpa perlu menulis ulang baris kode secara manual.

---

## 1. Analogi Konsep: Putaran Lari di Stadion

Bayangkan kamu sedang mengikuti tes lari keliling lapangan bola sebanyak 5 putaran:
- **Inisialisasi (`i := 1`):** Kamu berdiri di garis start dengan catatan: putaran ke-1.
- **Kondisi Berhenti (`i <= 5`):** Sebelum berlari, kamu mengecek wasit: *"Apakah putaranku masih belum lewat dari 5?"*. Kalau ya, kamu lari.
- **Badan Perulangan (Loop Body):** Kamu berlari menempuh 1 keliling lapangan.
- **Pencacah / Step (`i++`):** Begitu menyentuh garis start lagi, kamu mencatat: *"Putaranku bertambah 1"*.
- Begitu catatanmu mencapai 6, wasit meniup peluit tanda selesai, dan kamu berhenti berlari.

![Anatomi For Loop](../assets/images/for-loop-iteration.svg)

### Simulasi Animasi Siklus Putaran For-Loop
Berikut adalah animasi pelacakan (trace) nilai variabel counter `i` pada setiap tahapan perulangan Go:

![Animasi Eksekusi For Loop](../assets/images/for-loop-animation.gif)

---

## 2. Diagram Alur For-Loop

```mermaid
flowchart TD
    Init[Inisialisasi: i := 1] --> Cond{Apakah i <= N ?}
    Cond -->|True| Body[Jalankan Badan Loop]
    Body --> Step[Langkah Pencacah: i++]
    Step --> Cond
    Cond -->|False| Exit([Keluar dari Loop / Selesai])
```

---

## 3. Struktur Sintaks For di Go

Bahasa Go hanya memiliki satu kata kunci perulangan, yaitu `for`. Format standar perulangan dengan counter adalah:

```go
for inisialisasi; kondisi; step {
    // instruksi yang diulang
}
```

Contoh program mencetak angka 1 sampai 5:
```go
package main

import "fmt"

func main() {
    for i := 1; i <= 5; i++ {
        fmt.Println("Putaran ke-", i)
    }
}
```

---

## 4. Soal Latihan & Skeleton Code

### Soal 1: Penjumlahan Sekumpulan Bilangan (Deret 1 s.d. n)
Buatlah program untuk menjumlahkan deret bilangan dari 1 hingga $n$.
Masukan: Sebuah bilangan bulat positif $n$.
Keluaran: Total penjumlahan $1 + 2 + 3 + \dots + n$.
*Contoh:* Input `3` -> Output `6` ($1 + 2 + 3$).

#### Skeleton Code:
```go
package main

import "fmt"

func main() {
    var n int
    fmt.Scan(&n)

    total := 0
    // TODO: Gunakan for loop dari i := 1 hingga i <= n
    // TODO: Di dalam loop, tambahkan nilai i ke variabel total: total += i

    fmt.Println(total)
}
```

### Soal 2: Volume Sejumlah n Kerucut
Buatlah program untuk menghitung volume dari $n$ buah kerucut.
Masukan: Baris pertama bilangan $n$. Kemudian $n$ baris berikutnya masing-masing berisi jari-jari $r$ dan tinggi $t$ kerucut.
Rumus: $\text{Volume} = \frac{1}{3} \pi r^2 t$, dengan $\pi = 3.1415926535$.

#### Skeleton Code:
```go
package main

import "fmt"

const PI = 3.1415926535

func main() {
    var n int
    fmt.Scan(&n)

    // TODO: Buat perulangan for i := 0; i < n; i++
    // TODO: Di setiap iterasi, baca r dan t
    // TODO: Hitung volume = (1.0 / 3.0) * PI * r * r * t
    // TODO: Cetak volume
}
```

### Soal 3: Perkalian Tanpa Operator Kali (*)
Hitunglah hasil perkalian dua buah bilangan bulat positif $A \times B$ tanpa menggunakan operator `*`, melainkan dengan menjumlahkan bilangan $A$ sebanyak $B$ kali menggunakan perulangan.

#### Skeleton Code:
```go
package main

import "fmt"

func main() {
    var a, b int
    fmt.Scan(&a, &b)

    hasil := 0
    // TODO: Lakukan perulangan sebanyak b kali
    // TODO: Setiap putaran, tambahkan a ke dalam hasil
    // hasil += a

    fmt.Println(hasil)
}
```

### Soal 4: Perhitungan Faktorial (n!)
Buatlah program untuk menghitung nilai faktorial $n! = 1 \times 2 \times 3 \times \dots \times n$. Khusus untuk $0! = 1$.

#### Skeleton Code:
```go
package main

import "fmt"

func main() {
    var n int
    fmt.Scan(&n)

    faktorial := 1
    // TODO: Gunakan for loop dari i := 1 hingga i <= n
    // TODO: Kalikan faktorial dengan i pada setiap iterasi: faktorial *= i

    fmt.Println(faktorial)
}
```
