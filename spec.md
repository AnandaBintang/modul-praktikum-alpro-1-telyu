# Technical Specification: Repositori Pembelajaran Praktikum Alpro 1 Go Telkom University

## 1. Ringkasan Proyek
Repositori `modul-praktikum-alpro-1-telyu` bertujuan untuk menyediakan materi penjelasan interaktif, visual, dan ramah pemula berbasis bahasa pemrograman Go (Golang) untuk mata kuliah Algoritma dan Pemrograman 1 (CAK1BAB3) di S1 Informatika Telkom University. Repositori ini membedah 16 modul praktikum resmi ke dalam direktori terisolasi dengan penjelasan konsep beralogi nyata, diagram alur Mermaid, ilustrasi grafis lokal, serta skeleton kode latihan.

## 2. Struktur Direktori dan Penamaan
Repositori memiliki struktur direktori sebagai berikut:
```text
modul-praktikum-alpro-1-telyu/
├── README.md
├── spec.md
├── tickets.md
├── assets/
│   └── images/
│       ├── golang-concept.svg
│       ├── memory-variable-box.svg
│       ├── modulo-division.svg
│       ├── for-loop-iteration.svg
│       ├── nested-loop-grid.svg
│       ├── decision-railway.svg
│       ├── switch-case-junction.svg
│       ├── while-loop-gate.svg
│       ├── repeat-until-cycle.svg
│       ├── composite-control.svg
│       └── sequential-stream.svg
├── modul-1-running-modul/
│   └── README.md
├── modul-2-io-tipe-data-dan-variabel/
│   └── README.md
├── modul-3-io-tipe-data-dan-variabel-latihan-1/
│   └── README.md
├── modul-4-io-tipe-data-dan-variabel-latihan-2/
│   └── README.md
├── modul-5-for-loop/
│   └── README.md
├── modul-6-for-loop-2/
│   └── README.md
├── modul-7-asesmen-praktikum-1/
│   └── README.md
├── modul-8-asistensi-praktikum/
│   └── README.md
├── modul-9-if-then/
│   └── README.md
├── modul-10-else-if/
│   └── README.md
├── modul-11-switch-case/
│   └── README.md
├── modul-12-while-loop/
│   └── README.md
├── modul-13-repeat-until/
│   └── README.md
├── modul-14-komposisi/
│   └── README.md
├── modul-15-asesmen-praktikum-2/
│   └── README.md
└── modul-16-skema-pemrosesan-sekuensial/
    └── README.md
```

## 3. Ketentuan Desain & Konten
1. **Bahasa & Tone:**
   Bahasa Indonesia santai, ramah mahasiswa baru, dengan analogi konkret (misal: variabel sebagai wadah kardus berlabel, memory address sebagai nomor kavling tanah, for-loop sebagai putaran lari estafet, switch-case sebagai tombol dispenser).
2. **Kepatuhan Format (Strict No Emoji):**
   Sesuai direktif kualitas, seluruh deliverable (README, kode, markdown, commit message) tidak boleh mengandung karakter emoji.
3. **Komponen Setiap Modul:**
   - Ringkasan Inti & Analogi Konsep.
   - Ilustrasi visual lokal (`../assets/images/<file>.svg`).
   - Diagram interaktif Mermaid (`flowchart TD` / `flowchart LR`).
   - Bedah Sintaks Go (struktur kode dan penjelasannya).
   - Contoh Kode Program Lengkap yang Siap Dijalankan.
   - Soal Latihan & Skeleton Code (blok kode berisikan komentar `// TODO`, tipe data, format input/output, dan petunjuk langkah pengerjaan).
4. **Modul Asesmen & Asistensi (Modul 7, 8, 15):**
   Disusun dalam bentuk kerangka/skeleton review komprehensif, daftar materi yang diujikan, tips strategi penyelesaian masalah di lab, dan kisi-kisi latihan.

## 4. Publikasi Git & GitHub
- Git Config: `user.name = "AnandaBintang"`, `user.email = "anandabintang4@gmail.com"`.
- Remote: `https://github.com/AnandaBintang/modul-praktikum-alpro-1-telyu.git`.
- Visibilitas: Public.
