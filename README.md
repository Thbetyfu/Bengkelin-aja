# Bengkelin

Bengkelin adalah aplikasi web untuk memesan jadwal servis di bengkel motor, baik untuk motor konvensional (bensin) maupun motor listrik. Pengguna dapat mendaftarkan kendaraan, memilih bengkel dan layanan, menyimpan riwayat servis, dan mendapat pengingat servis berikutnya.

- **Nama Lengkap:** Thoriq
- **NIM:** 103022430006
- **Mata Kuliah:** Pemrograman Web Fullstack

## Tugas Pekan 2 - Struktur HTML

Pada pekan ini proyek hanya berisi **struktur HTML murni** tanpa CSS (tidak ada tag `<style>`, atribut `style`, maupun framework) dan tanpa JavaScript. Fokus tugas:

1. Minimal 3 halaman dengan elemen dasar HTML (heading, paragraf, hyperlink, tabel, gambar, dan elemen formulir).
2. Penggunaan elemen semantic HTML5 sebagai pengganti `<div>` yang bertumpuk.
3. Aksesibilitas dasar: atribut `alt` pada setiap gambar dan `<label>` yang terhubung ke setiap input.
4. Screenshot setiap halaman dalam kondisi tanpa gaya (unstyled).

Semua data pada halaman (kendaraan, bengkel, harga, teknisi) adalah data contoh fiktif.

## Daftar Halaman

| File | Halaman | Fungsi |
| --- | --- | --- |
| `index.html` | Beranda - Riwayat & Jadwal Servis | Halaman utama: pengingat servis berikutnya, tabel riwayat booking servis (dengan tautan Detail dan Edit), daftar kendaraan saya, dan tips perawatan. |
| `booking.html` | Form Booking Servis | Formulir untuk menambah atau mengedit booking: data kendaraan, pilihan bengkel dan layanan, jadwal, kontak, keluhan, dan opsi pengingat servis. |
| `detail.html` | Detail Servis | Detail satu booking servis: informasi kendaraan, informasi servis, rincian biaya, catatan teknisi, dan pengingat servis berikutnya. |
| `bengkel.html` | Daftar Bengkel | Daftar bengkel mitra beserta alamat, layanan untuk motor konvensional dan motor listrik, serta jam buka. |

## Struktur Folder

```
bengkelin/
├── .gitignore
├── .htmlvalidate.json
├── README.md
├── index.html
├── booking.html
├── detail.html
├── bengkel.html
├── assets/
│   ├── css/
│   │   └── .gitkeep
│   ├── images/
│   │   ├── bengkel.svg
│   │   ├── logo-bengkelin.svg
│   │   ├── motor-konvensional.svg
│   │   └── motor-listrik.svg
│   └── js/
│       └── .gitkeep
└── docs/
    └── screenshots/
        ├── 01-beranda.png
        ├── 02-booking.png
        ├── 03-detail.png
        └── 04-daftar-bengkel.png
```

Folder `assets/css/` dan `assets/js/` sengaja disiapkan (masih kosong) untuk pekan berikutnya. File `.htmlvalidate.json` adalah konfigurasi kecil untuk validator HTML (`html-validate`).

## Penerapan Semantic HTML5

- `<header>`: kepala halaman di setiap halaman (logo, nama situs, navigasi) dan kepala `<article>` pada halaman detail.
- `<nav>`: navigasi utama di setiap halaman, ditambah navigasi breadcrumb pada `detail.html`. Setiap `<nav>` diberi `aria-label` yang berbeda.
- `<main>`: konten utama setiap halaman (satu `<main>` per halaman).
- `<section>`: pengelompokan konten bertema, misalnya "Pengingat Servis Berikutnya", "Riwayat Booking Servis", "Kendaraan Saya", "Rincian Biaya", dan "Catatan Teknisi".
- `<article>`: konten yang berdiri sendiri, yaitu setiap kendaraan pada "Kendaraan Saya", detail satu booking servis, dan setiap bengkel pada `bengkel.html`.
- `<aside>`: konten pendukung, yaitu "Tips Perawatan" di beranda dan ilustrasi jenis motor di halaman booking.
- `<footer>`: kaki halaman berisi hak cipta dan identitas pembuat, serta kaki `<article>` berisi tautan kembali dan edit.
- `<figure>` dan `<figcaption>`: ilustrasi motor beserta keterangannya.
- `<time datetime="...">`: semua tanggal dan jam agar dapat dibaca mesin.
- `<dl>`, `<dt>`, `<dd>`: pasangan label dan nilai pada informasi kendaraan dan informasi servis.
- `<table>` dengan `<thead>`, `<tbody>`, `<tfoot>`: data tabular riwayat servis dan rincian biaya (total di `<tfoot>`).
- `<form>`, `<fieldset>`, `<legend>`: pengelompokan isian formulir booking.

## Penerapan Aksesibilitas

- `<html lang="id">` di setiap halaman agar pembaca layar menggunakan pelafalan Bahasa Indonesia.
- Setiap `<img>` memiliki `alt` deskriptif dalam Bahasa Indonesia serta atribut `width` dan `height`.
- Setiap `<input>`, `<select>`, dan `<textarea>` memiliki `id` unik dan tepat satu `<label for="...">` yang cocok.
- Tombol radio "Jenis Motor" dikelompokkan dalam `<fieldset>` dengan `<legend>`, dan setiap radio memiliki label sendiri.
- Bagian formulir dikelompokkan dengan `<fieldset>` dan `<legend>` (Data Kendaraan, Pilih Bengkel & Layanan, Jadwal Servis, Kontak, Keluhan dan Catatan).
- Pilihan layanan dikelompokkan dengan `<optgroup>` ("Motor Konvensional", "Motor Listrik", dan "Umum").
- Atribut `required`, `type` yang sesuai (`date`, `time`, `tel`, `email`, `number`), dan `autocomplete` pada data kontak.
- Tabel memiliki `<caption>` dan `<th scope="col">` / `<th scope="row">`.
- Tautan "Detail" dan "Edit" di tabel diberi `aria-label` yang menyebut nomor booking agar tidak ambigu.
- Tautan "Langsung ke konten utama" di awal halaman, `aria-current="page"` pada menu aktif, dan hierarki heading yang runtut (satu `<h1>` per halaman).

Validasi: semua halaman lolos `html-validate` (preset `html-validate:recommended`) dan W3C Nu HTML Checker tanpa error maupun peringatan.

## Screenshot

Screenshot halaman penuh dalam kondisi tanpa CSS.

### 1. Beranda - Riwayat & Jadwal Servis (`index.html`)

![Screenshot halaman Beranda](docs/screenshots/01-beranda.png)

### 2. Form Booking Servis (`booking.html`)

![Screenshot halaman Form Booking Servis](docs/screenshots/02-booking.png)

### 3. Detail Servis (`detail.html`)

![Screenshot halaman Detail Servis](docs/screenshots/03-detail.png)

### 4. Daftar Bengkel (`bengkel.html`)

![Screenshot halaman Daftar Bengkel](docs/screenshots/04-daftar-bengkel.png)

## Rencana Pengembangan

- **Pekan 3:** menambahkan CSS (file di `assets/css/`) untuk tata letak, warna, dan tipografi.
- **Pekan 4:** menerapkan framework CSS (Bootstrap atau Tailwind) agar tampilan responsif.
- **Pekan berikutnya:** menambahkan JavaScript untuk interaksi di sisi klien, lalu backend dan database untuk menyimpan data pengguna, kendaraan, booking, dan riwayat servis, serta fitur pengingat servis otomatis.
