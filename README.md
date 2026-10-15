# LAPORAN PRAKTIKUM DESAIN WEB A
## Pertemuan 5: Desain Kerangka Website, Wireframe, dan Struktur Informasi 
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Status](https://img.shields.io/badge/Status-Selesai-success)

---

## 📋 Identitas Praktikan

| | |
|---|---|
| **Nama** | Ilham Baihaqi |
| **NIM** | 4525210029 |
| **Program Studi** | Teknik Informatika |
| **Fakultas** | Teknik |
| **Universitas** | Universitas Pancasila |
| **Mata Kuliah** | Praktikum Desain Web A |
| **Pertemuan** | 5 |

---

## 1. Tujuan Praktikum

1. Memahami cara merancang kerangka (*wireframe*) sebuah website sebelum diberi tampilan akhir.
2. Menyusun struktur informasi halaman yang terdiri dari *header*, *navbar*, *sidebar*, konten utama, *card*, dan *footer*.
3. Membuat dua versi wireframe yang berbeda: **Contoh 1** (Low Fidelity Wireframe) dan **Contoh 2** (Wireframe Portal Sekolah).
4. Menerapkan **Flexbox** pada Contoh 1 dan **CSS Grid** pada Contoh 2 untuk mengatur tata letak.
5. Menerapkan *media query* agar tampilan menyesuaikan layar desktop, tablet, dan ponsel.
6. Memisahkan struktur (`index.html`) dan tampilan (`style.css`) ke dalam *file* yang berbeda.
7. Mendokumentasikan hasil tampilan desktop dan mobile.

---

## 2. Dasar Teori

### 2.1 Wireframe
*Wireframe* adalah rancangan kerangka halaman web yang menunjukkan **letak** elemen-elemen utama tanpa memikirkan warna, gambar, atau gaya yang rumit. Fungsinya seperti denah rumah: kita menentukan dulu di mana ruang tamu dan kamar, baru kemudian dihias.

| Jenis | Keterangan |
|---|---|
| **Low Fidelity** | Sangat sederhana, hanya kotak dan teks pengganti (*placeholder*), fokus pada posisi elemen |
| **High Fidelity** | Sudah mendekati tampilan akhir (warna, font, gambar, ikon) |

Pada praktikum ini, Contoh 1 lebih mendekati *low fidelity*, sedangkan Contoh 2 sudah memiliki struktur informasi yang lebih lengkap seperti sebuah portal.

### 2.2 Struktur Informasi
Struktur informasi adalah cara mengelompokkan dan mengurutkan isi halaman agar pengguna mudah menemukan apa yang dicari. Elemen yang umum dipakai:

| Elemen | Fungsi |
|---|---|
| **Header** | Identitas website (logo dan nama) |
| **Navbar** | Menu navigasi utama |
| **Sidebar** | Menu tambahan di samping konten |
| **Hero / Banner** | Bagian pembuka yang berisi judul utama dan *call to action* |
| **Card** | Kotak informasi singkat yang dapat disusun berulang |
| **Footer** | Informasi kontak dan hak cipta |

### 2.3 Flexbox dan CSS Grid

| | Flexbox | CSS Grid |
|---|---|---|
| **Dimensi** | Satu dimensi (baris atau kolom) | Dua dimensi (baris dan kolom sekaligus) |
| **Properti utama** | `display: flex`, `flex-direction`, `flex`, `gap` | `display: grid`, `grid-template-columns`, `gap` |
| **Cocok untuk** | Navbar, deretan card | Layout halaman, grid card |

### 2.4 Media Query
*Media query* adalah aturan CSS yang hanya berlaku pada kondisi tertentu, misalnya lebar layar.

```css
@media (max-width: 768px) {
  /* aturan khusus layar di bawah 768px */
}
```

---

## 3. Alat dan Bahan

| Kategori | Keterangan |
|---|---|
| **Bahasa** | HTML5 dan CSS3 |
| **Text Editor** | Visual Studio Code _(sesuaikan)_ |
| **Browser** | Google Chrome / Microsoft Edge _(sesuaikan)_ |
| **Version Control** | Git dan GitHub |
| **Aset Gambar** | Logo, seragam, SPMB, dan kepala sekolah SMK Bunda Kandoeng (format PNG) |

---

## 4. Struktur Proyek

```
Prak_DW_A-Pertemuan-5/
├── Contoh 1/
│   ├── index.html                  
│   ├── css/
│   │   └── style.css
│   ├── images/                     # bk, basis, spmb, seragam, kepsek
│   └── dokumentasi/                # Screenshot desktop dan mobile
├── Contoh 2/
│   ├── index.html                 
│   ├── css/
│   │   └── style.css
│   ├── images/                     # bk, spmb, seragam, kepsek
│   └── dokumentasi/                # Screenshot desktop dan mobile
├── Tugas/
│   ├── index.html
│   ├── css/
│   │   └── style.css
│   ├── images/                     # pb, 2kb, artm, idm, boibz
│   └── dokumentasi/                # Screenshot desktop dan mobile
├── Materi/                         # Modul pertemuan 5
└── README.md                       # Laporan praktikum
```

---

## 5. Pembahasan dan Hasil

### 5.1 Studi Kasus

Studi kasus yang dipakai adalah website **SMK Bunda Kandoeng**. Halaman dirancang sebagai kerangka informasi sekolah yang memuat pendaftaran (SPMB), seragam sekolah, dan profil kepala sekolah. Dibuat dua versi agar dapat dibandingkan:

- **Contoh 1** berupa halaman informasi sederhana dengan sidebar dan tiga *card* konten.
- **Contoh 2** berupa portal sekolah yang lebih lengkap, dengan menu siswa, informasi sekolah, dan layanan siswa.

Selain dua contoh tersebut, ada satu halaman lagi di folder **Tugas**, yaitu wireframe portal berita bertema turnamen Point Blank (berita utama, daftar terpopuler, dan tiga berita terbaru).

### 5.2 Menghubungkan HTML dengan CSS

Kedua contoh memakai satu *file* CSS eksternal agar kode tidak tersebar.

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="css/style.css">
</head>
```

Tag `meta viewport` wajib ada supaya tampilan di ponsel tidak ikut diperkecil seperti layar desktop.

---

### 5.3 Contoh 1: 
#### Struktur HTML

```html
<header class="header">   <!-- logo dan judul -->
<nav class="navbar">      <!-- Beranda, Tentang, Produk, Kontak -->
<main class="layout">
  <aside class="sidebar"> <!-- menu samping -->
  <section class="content">
    <div class="hero">           <!-- gambar, judul, deskripsi, tombol -->
    <div class="card-container"> <!-- tiga card -->
  </section>
</main>
<footer class="footer">   <!-- kontak -->
```

| Bagian | Fungsi |
|---|---|
| `header` | Logo SMK Bunda Kandoeng |
| `navbar` | Empat menu navigasi utama |
| `sidebar` | Daftar menu samping (Menu 1 sampai Menu 4) |
| `hero` | Gambar, judul "SMK Bunda Kandoeng", deskripsi, dan tombol *Call to Action* |
| `card-container` | Tiga *card*: SPMB, Seragam, Kepala Sekolah |
| `footer` | Telepon, WhatsApp, dan email sekolah |

#### Penerapan CSS

Warna dikelola lewat **variabel CSS** di `:root` supaya mudah diganti dari satu tempat.

```css
:root {
  --biru-tua: #1f3a5f;
  --latar: #f3f5f8;
  --aksen: #e0a526;
}

* { box-sizing: border-box; }
```

Layout utama memakai Flexbox, yaitu sidebar di kiri dan konten di kanan:

```css
.layout {
  display: flex;
  gap: 20px;
}

.sidebar { width: 220px; flex-shrink: 0; }
.content { flex: 1; min-width: 0; }
```

Tiga *card* disusun sejajar dengan lebar yang sama:

```css
.card-container {
  display: flex;
  gap: 20px;
}

.card { flex: 1; }
```

#### Media Query

```css
@media (max-width: 768px) {
  .layout          { flex-direction: column; }
  .card-container  { flex-direction: column; }
  .navbar          { flex-wrap: wrap; }
}
```

Pada layar di bawah 768px, sidebar pindah ke atas konten dan ketiga *card* tersusun ke bawah dalam satu kolom.

#### Hasil Tampilan Contoh 1

**Desktop:**

<img width="1917" height="1078" alt="Desktop - Preview" src="https://github.com/user-attachments/assets/b6d86374-17f4-44ad-bee9-a87dd36061ba" />


**Mobile:**

<img width="630" height="1078" alt="Mobile - Preview (1)" src="https://github.com/user-attachments/assets/5cebd28a-f522-4623-b986-4d4502e3745e" />
<img width="625" height="845" alt="Mobile - Preview (2)" src="https://github.com/user-attachments/assets/78cfde05-b02b-45e2-b95b-0ffb42516c73" />


---

### 5.4 Contoh 2:

#### Struktur HTML

```html
<header>
  <div class="container header-wrapper"> <!-- brand + profil -->
<nav>
  <div class="container nav-wrapper">    <!-- 5 menu -->
<main class="container main-layout">
  <aside class="sidebar">                <!-- menu sekolah -->
  <section class="content">
    <section id="beranda" class="hero">
    <section id="informasi">             <!-- tiga card -->
    <section id="layanan">               <!-- empat item layanan -->
</main>
<footer id="kontak">
```

| Bagian | Fungsi |
|---|---|
| `header` | Logo, judul "Portal Sekolah", dan label profil "Siswa" |
| `nav` | Beranda, Informasi, Jadwal, Layanan, Kontak (memakai *anchor link* `#`) |
| `sidebar` | Dashboard, Profil Siswa, Jadwal Pelajaran, Nilai Rapor, Absensi, Pembayaran SPP |
| `hero` | Teks sambutan, tombol, dan logo sekolah |
| `informasi` | Tiga *card* dengan tautan: SPMB, Seragam, Kepala Sekolah |
| `layanan` | Empat kotak layanan: Jadwal Pelajaran, Nilai Rapor, Absensi, Administrasi |
| `footer` | Nama portal dan email sekolah |

#### Penerapan CSS

Class `.container` dipakai berulang untuk membatasi lebar konten dan menengahkannya:

```css
.container {
  width: 90%;
  max-width: 1200px;
  padding: 20px;
  margin: auto;
}
```

Tata letak halaman memakai **CSS Grid** dua kolom (sidebar dan konten):

```css
.main-layout {
  display: grid;
  grid-template-columns: 230px 1fr;
  gap: 25px;
  align-items: start;
}
```

Bagian *hero*, *card*, dan layanan juga memakai Grid:

```css
.hero       { display: grid; grid-template-columns: 2fr 1fr; }
.card-grid  { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
.layanan-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 15px; }
```

Unit `fr` membagi sisa ruang secara proporsional. Misalnya `2fr 1fr` berarti kolom teks mendapat dua bagian dan kolom gambar satu bagian.

#### Media Query (Dua Breakpoint)

| Breakpoint | Perubahan |
|---|---|
| **≤ 900px (tablet)** | Layout menjadi satu kolom, sidebar berubah menjadi deretan tombol, *card* dan layanan menjadi 2 kolom |
| **≤ 600px (ponsel)** | Header dan navbar menjadi vertikal, *hero*, *card*, dan layanan menjadi 1 kolom, footer ditumpuk |

```css
@media (max-width: 900px) {
  .main-layout { grid-template-columns: 1fr; }
  .card-grid   { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 600px) {
  .hero       { grid-template-columns: 1fr; }
  .card-grid  { grid-template-columns: 1fr; }
}
```

#### Hasil Tampilan Contoh 2

**Desktop:**

<img width="1917" height="1078" alt="Desktop - Preview" src="https://github.com/user-attachments/assets/1431d14c-30b7-43b0-8db3-8c50563db142" />


**Mobile:**

<img width="627" height="1078" alt="Mobile - Preview (1)" src="https://github.com/user-attachments/assets/f9616c2e-5d5b-47d0-8065-de54fa481b40" />
<img width="606" height="1078" alt="Mobile - Preview (2)" src="https://github.com/user-attachments/assets/1ca0e704-54da-4a6f-a5f3-c906df53cd34" />

---

### 5.5 Tugas: Wireframe Portal Berita (Turnamen Point Blank)

Pada Tugas ini saya membuat wireframe portal berita dengan tema esports. Isi beritanya seputar turnamen Point Blank terbaru: 2KB DYNASTY juara Point Blank Star Battle Season 2 dan jadwal PBNC XVII di JICC Senayan. Tata letaknya memakai gabungan Flexbox (header dan navbar) dan CSS Grid (layout halaman dan card).

#### Struktur HTML

```html
<header class="area header">
  <div class="container header-wrapper"> <!-- hamburger, logo, judul, search, tombol Masuk -->
<nav class="area navbar">
  <div class="container nav-wrapper">    <!-- 6 menu -->
<main class="container">
  <div class="top-layout">
    <section class="area headline">      <!-- berita utama -->
    <aside class="area populer">         <!-- daftar terpopuler -->
  </div>
  <section class="area daftar">
    <div class="card-grid">              <!-- tiga card berita -->
</main>
<footer class="area footer">
```

| Bagian | Fungsi |
|---|---|
| `header` | Logo Point Blank, judul "Portal Berita", kolom pencarian, dan tombol Masuk |
| `navbar` | Beranda, Nasional, Ekonomi, Olahraga, Teknologi, Esports (menu aktif: Esports) |
| `headline` | Berita utama: foto, kategori dan tanggal, judul, isi berita, dan sumber |
| `populer` | Daftar lima berita terpopuler (memakai `<ol>`) |
| `daftar` | Tiga *card* Berita Terbaru: ARTM HFS ULTIMATE, PBNC XVII, dan Reborn KRS |
| `footer` | Hak cipta portal |

#### Penerapan CSS

Warna disimpan di variabel CSS pada `:root`, jadi kalau mau ganti tema cukup ubah di satu tempat. Palet yang dipakai adalah biru gelap (navy) dengan aksen oranye.

```css
:root {
    --navy: #0f172a;
    --navy2: #1e293b;
    --aksen: #f97316;
    --aksen-gelap: #ea580c;
    --teks: #1e293b;
}
```

Class `.container` dipakai ulang di header, navbar, konten, dan footer supaya lebar kontennya sama dan berada di tengah:

```css
.container {
    width: 92%;
    max-width: 1100px;
    margin: 0 auto;
}
```

Bagian atas halaman memakai CSS Grid dua kolom, berita utama dapat dua bagian dan terpopuler satu bagian. Tiga *card* di bawahnya juga memakai Grid:

```css
.top-layout {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 25px;
    align-items: start;
}

.card-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Header dan navbar memakai Flexbox karena susunannya satu baris. Kolom pencarian diberi `flex: 1` supaya mengisi sisa ruang di antara judul dan tombol Masuk:

```css
.header-wrapper { display: flex; align-items: center; gap: 15px; }
.search         { display: flex; flex: 1; gap: 8px; }
.nav-wrapper    { display: flex; }
```

Untuk foto, saya memakai `object-fit: contain` agar gambar tidak terpotong. Di HTML juga ada `onerror` pada tag `img`: kalau gambar gagal dimuat, gambar disembunyikan dan diganti teks keterangan foto, jadi kotaknya tetap terlihat seperti wireframe.

#### Media Query (Dua Breakpoint)

| Breakpoint | Perubahan |
|---|---|
| **≤ 900px (tablet)** | *Card* berita menjadi 2 kolom |
| **≤ 700px (ponsel)** | Tombol hamburger muncul dan navbar disembunyikan, kolom pencarian pindah ke baris sendiri, berita utama dan terpopuler ditumpuk, *card* menjadi 1 kolom, footer ditumpuk |

```css
@media (max-width: 900px) {
    .card-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 700px) {
    .menu-toggle { display: block; }
    .navbar      { display: none; }
    .search      { order: 5; flex-basis: 100%; }

    .top-layout,
    .card-grid   { grid-template-columns: 1fr; }
}
```

Karena ini masih wireframe, tombol hamburger belum diberi fungsi (belum ada JavaScript), jadi fungsinya hanya sebagai penanda posisi menu di tampilan ponsel.

#### Hasil Tampilan Tugas

**Desktop:**

![Tampilan Desktop (1)](Tugas/dokumentasi/Tampilan%20-%20Desktop%20(1).png)
![Tampilan Desktop (2)](Tugas/dokumentasi/Tampilan%20-%20Desktop%20(2).png)

**Mobile:**

![Tampilan Mobile (1)](Tugas/dokumentasi/Tampilan%20-%20Mobile%20(1).png)
![Tampilan Mobile (2)](Tugas/dokumentasi/Tampilan%20-%20Mobile%20(2).png)
![Tampilan Mobile (3)](Tugas/dokumentasi/Tampilan%20-%20Mobile%20(3).png)

---

## 6. Perbandingan Contoh 1 dan Contoh 2

| Aspek | Contoh 1 | Contoh 2 |
|---|---|---|
| **Judul halaman** | Low Fidelity Wireframe | Wireframe Portal Sekolah |
| **Teknik layout utama** | Flexbox | CSS Grid |
| **Navbar** | 4 menu | 5 menu (anchor link ke section) |
| **Sidebar** | Menu 1 sampai 4 (teks biasa) | 6 menu sekolah (link) |
| **Hero** | Satu kolom, rata tengah | Dua kolom (teks dan gambar) |
| **Card** | 3 card (Flexbox) | 3 card (Grid) dengan tautan |
| **Bagian tambahan** | Tidak ada | Layanan Siswa (4 kotak) |
| **Pengelolaan warna** | Variabel CSS (`:root`) | Kode warna langsung |
| **Jumlah breakpoint** | 1 (768px) | 2 (900px dan 600px) |
| **Tingkat detail** | Lebih sederhana | Lebih lengkap seperti portal |

---

## 7. Rekap Properti CSS yang Digunakan

| Kategori | Properti |
|---|---|
| **Teks** | `color`, `font-family`, `font-size`, `font-weight`, `line-height`, `text-align`, `text-decoration`, `letter-spacing` |
| **Latar** | `background-color` |
| **Box model** | `box-sizing`, `width`, `max-width`, `min-height`, `margin`, `padding` |
| **Border** | `border`, `border-bottom`, `border-radius` |
| **Flexbox** | `display: flex`, `flex-direction`, `flex`, `flex-wrap`, `flex-shrink`, `gap`, `justify-content`, `align-items` |
| **Grid** | `display: grid`, `grid-template-columns`, `repeat()`, `fr` |
| **Gambar** | `object-fit`, `max-width`, `max-height` |
| **Variabel** | `:root`, `var(--nama)` |
| **Selector** | elemen, class (`.`), id (`#`), pseudo-class (`:hover`, `:last-child`) |
| **Responsive** | `@media (max-width: ...)` |

---

## 8. Cara Menjalankan

1. **Clone repositori**
```bash
   git clone https://github.com/IlhamBaihaqi24/Prak_DW_A-Pertemuan-5.git
```
2. **Masuk ke folder proyek**
```bash
   cd Prak_DW_A-Pertemuan-5
```
3. **Buka file HTML di browser**: `Contoh 1/index.html`, `Contoh 2/index.html`, atau `Tugas/index.html`, dengan klik dua kali atau memakai ekstensi *Live Server* di VS Code.
4. **Uji tampilan mobile**: tekan `F12` di browser, lalu aktifkan *Toggle Device Toolbar* (`Ctrl + Shift + M`).

> ⚠️ Folder `css/` dan `images/` harus berada satu level dengan `index.html`, dan penulisan path harus persis sama (perhatikan huruf besar/kecil).

---

## 9. Kesimpulan

Dari praktikum Pertemuan 5 ini dapat disimpulkan bahwa:

1. *Wireframe* membantu menentukan letak *header*, *navbar*, *sidebar*, konten, dan *footer* sebelum halaman diberi tampilan akhir, sehingga struktur informasi menjadi lebih jelas.
2. **Flexbox** cocok untuk susunan satu arah seperti navbar dan deretan *card*, sedangkan **CSS Grid** lebih praktis untuk layout dua dimensi seperti halaman dengan sidebar dan grid *card*.
3. **Media query** membuat halaman menyesuaikan ukuran layar. Contoh 1 cukup satu *breakpoint*, sedangkan Contoh 2 memakai dua *breakpoint* agar tampilan tablet dan ponsel lebih nyaman.
4. Penggunaan **variabel CSS** (Contoh 1) dan class berulang seperti `.container` (Contoh 2) membuat kode lebih rapi dan mudah dirawat.
5. Memisahkan `index.html` dan `style.css` membuat struktur dan tampilan mudah diubah tanpa saling mengganggu.
6. Pada Tugas, gabungan Flexbox untuk header dan navbar serta CSS Grid untuk layout halaman dan *card* berita membuat tampilan portal berita rapi di desktop. Dua *breakpoint* (900px dan 700px) cukup untuk menyesuaikannya ke tablet dan ponsel.

Materi ini menjadi dasar sebelum melanjutkan ke pembuatan website yang lebih lengkap pada pertemuan berikutnya.

---

<p align="center">
  <sub>© 2026 Ilham Baihaqi (4525210029) · Teknik Informatika · Universitas Pancasila</sub>
</p>
