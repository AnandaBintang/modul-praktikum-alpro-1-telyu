# Modul 8: Asistensi Praktikum (Evaluasi & Refleksi)

Modul 8 difokuskan untuk sesi asistensi bersama Asisten Laboratorium dan Asisten Praktikum guna mengevaluasi hasil Asesmen 1, meninjau kesalahan umum kode, serta mempersiapkan materi paruh kedua praktikum (percabangan dan logika lanjutan).

---

## 1. Kesalahan Umum yang Sering Terjadi di Paruh Pertama

1. **Lupa Menambahkan Tanda Ampersand (`&`) pada Input:**
   ```go
   // Salah:
   fmt.Scan(nilai) // Compiler panik atau data tidak tersimpan
   // Benar:
   fmt.Scan(&nilai) // Mengirimkan alamat memori
   ```

2. **Pembagian Integer yang Menghasilkan 0:**
   ```go
   // Salah:
   hasil := 1 / 2 // hasil bernilai 0 karena keduanya integer!
   // Benar:
   hasil := 1.0 / 2.0 // hasil bernilai 0.5
   ```

3. **Infinite Loop pada For:**
   Variabel counter lupa di-increment atau kondisi terminasi selalu bernilai `true`.

---

## 2. Jembatan Menuju Paruh Kedua Praktikum

Pada Modul 9 sampai dengan Modul 16, materi akan melangkah ke pengambilan keputusan komputasional:
- Percabangan: `If-Then`, `Else-If`, dan `Switch-Case`
- Perulangan Kondisional: `While-Loop` dan `Repeat-Until`
- Komposisi Struktur Kontrol Kompleks
- Skema Pemrosesan Data Sekuensial
