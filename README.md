# Praktikum 4 - CSS Layout

**Nama:** Manuel Johansen Dolok Saribu  
**NIM:** 312410493  
**Mata Kuliah:** Pemrograman Web  
**Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.  

## 1. Persiapan
Langkah awal:
- Buat folder baru bernama **Lab4Web**.
- Buat file **lab4_box.html** di dalam folder tersebut.

Isi dasar file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Box Element</title>
</head>
<body>
  <header>
    <h1>Box Element</h1>
  </header>
</body>
</html>
```

Langkah pertama bertujuan untuk menyiapkan struktur awal dokumen HTML.  
Mahasiswa membuat file **`lab4_box.html`** dan menuliskan struktur dasar HTML dengan tag `<html>`, `<head>`, dan `<body>`.  
Hasilnya adalah halaman kosong yang siap digunakan untuk menampilkan elemen layout menggunakan CSS.

---

## 2. Membuat Box Element
Tambahkan elemen `<div>` ke dalam file untuk membuat tiga kotak:
```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
</section>
```

Lalu tambahkan CSS di dalam tag `<style>`:
```html
<style>
  div {
    float: left;
    padding: 10px;
  }
  .div1 { background: red; }
  .div2 { background: yellow; }
  .div3 { background: green; }
</style>
```

Pada tahap ini, mahasiswa belajar mengenal **konsep box element**, yaitu bahwa setiap elemen HTML dianggap sebagai sebuah kotak.  
Tiga buah elemen `<div>` dibuat dengan class berbeda (`div1`, `div2`, `div3`) untuk mempraktikkan cara pengaturan tata letak dan warna menggunakan CSS.  
Hasil yang diharapkan adalah tiga kotak berwarna merah, kuning, dan hijau yang tampil sejajar secara horizontal.

---

## 3. Menambahkan Clearfix
Tambahkan elemen keempat setelah div3:
```html
<div class="div4">Div 4</div>
```

Dan tambahkan CSS:
```css
.div4 {
  background-color: blue;
  clear: left;
  float: none;
}
```

Langkah ini bertujuan untuk memahami fungsi **properti `clear`** pada CSS.  
Ketika elemen-elemen diatur menggunakan `float`, elemen berikutnya bisa ikut “terangkat”.  
Dengan menambahkan elemen baru (`div4`) dan menerapkan `clear: left;`, elemen tersebut akan ditempatkan di bawah tiga kotak pertama.  
Hasilnya adalah kotak keempat (biru) tampil di baris baru, tidak sejajar dengan kotak sebelumnya.

---

## 4. Membuat Layout Web Sederhana
Buat folder baru **lab4_layout**  
Di dalamnya buat dua file:
- `home.html`
- `style.css`

Isi **home.html**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layout Sederhana</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div id="container">
    <header>
      <h1>Layout Sederhana</h1>
    </header>
    <nav>
      <a href="home.html" class="active">Home</a>
      <a href="artikel.html">Artikel</a>
      <a href="about.html">About</a>
      <a href="kontak.html">Kontak</a>
    </nav>
    <section id="hero">
      <h1>Hello World!</h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit...</p>
      <a href="#" class="btn btn-large">Learn more »</a>
    </section>
    <section id="wrapper">
      <section id="main"></section>
      <aside id="sidebar"></aside>
    </section>
    <footer>
      <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
  </div>
</body>
</html>
```

Setelah memahami dasar box element, langkah ini berfokus pada pembuatan **struktur layout halaman web** secara keseluruhan.  
Mahasiswa membuat folder baru bernama **`lab4_layout`** dan dua file, yaitu `home.html` dan `style.css`.  
Struktur HTML disusun menggunakan **elemen semantik HTML5** seperti:
- `<header>` untuk bagian kepala halaman,  
- `<nav>` untuk navigasi,  
- `<section>` untuk area konten utama,  
- `<aside>` untuk sidebar, dan  
- `<footer>` untuk bagian bawah halaman.

---

## 5. Menambahkan Style (style.css)
```css
/* Reset dan Font */
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Open Sans', sans-serif;
  color: #5a5a5a;
}

/* Container */
#container {
  width: 980px;
  margin: 0 auto;
  box-shadow: 0 0 1em #ccc;
}

/* Header */
header {
  padding: 20px;
}
header h1 {
  color: #b5b5b5;
}

/* Navigasi */
nav {
  background-color: #1f5faa;
}
nav a {
  padding: 15px 30px;
  display: inline-block;
  color: #fff;
  font-weight: bold;
  text-decoration: none;
}
nav a.active,
nav a:hover {
  background-color: #2b83ea;
}

/* Hero Section */
#hero {
  background-color: #e4e4e5;
  padding: 50px 20px;
  margin-bottom: 20px;
}

/* Layout */
#wrapper { margin: 0; }
#main {
  float: left;
  width: 640px;
  padding: 20px;
}
#sidebar {
  float: left;
  width: 260px;
  padding: 20px;
}

/* Sidebar Widget */
.widget-box {
  border: 1px solid #eee;
  margin-bottom: 20px;
}
.widget-box .title {
  padding: 10px 16px;
  background-color: #428bca;
  color: #fff;
}

/* Footer */
footer {
  clear: both;
  background-color: #1d1d1d;
  padding: 20px;
  color: #eee;
}
```

Tahap ini digunakan untuk memperindah tampilan layout menggunakan CSS.  
Beberapa bagian penting yang diatur meliputi:
- Reset margin dan padding pada seluruh elemen,  
- Penentuan lebar layout (`width: 980px;`),  
- Pewarnaan header dan navigasi,  
- Penataan **hero section** agar terlihat menarik.  

Hasil akhirnya, halaman memiliki tampilan layout yang terpusat dengan navigasi berwarna biru, header berwarna abu muda, dan area konten siap diisi.

---

## 6. Menambahkan Widget Sidebar
Isi `<aside>` dengan widget:
```html
<aside id="sidebar">
  <div class="widget-box">
    <h3 class="title">Widget Header</h3>
    <ul>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
    </ul>
  </div>
</aside>
```

Pada langkah ini, mahasiswa belajar membuat **sidebar** yang berisi kumpulan widget seperti tautan atau informasi tambahan.  
Elemen `<aside>` digunakan untuk memisahkan konten utama dan sidebar, kemudian diatur menggunakan CSS agar menempel di sisi kanan layout.  
Hasil akhirnya, sidebar tampil sebagai kolom tambahan dengan judul dan daftar tautan.

---

## 7. Menambahkan Konten di Main Section
```html
<section id="main">
  <div class="row">
    <div class="box">
      <img src="https://dummyimage.com/120/db7d25/fff.png" alt="" class="image-circle">
      <h3>Heading</h3>
      <p>Contoh teks artikel.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>
  </div>
</section>
```

Langkah ini berfokus pada penambahan konten utama berupa tiga kolom kotak (`div.box`).  
Setiap kotak berisi gambar lingkaran, judul, paragraf, dan tombol.  
Dengan menggunakan properti `float` dan `width: 33.33%`, ketiga kotak ditampilkan sejajar.  
Hasilnya adalah tampilan konten utama yang rapi seperti layout website profesional.

---

## 8. Menambahkan Artikel
Tambahkan konten artikel di bawah main:
```html
<hr class="divider" />
<article class="entry">
  <h2>Featurette Heading</h2>
  <img src="https://dummyimage.com/150/7b8a70/fff.png" alt="">
  <p>Lorem ipsum dolor sit amet...</p>
</article>
```

Tahap ini mengajarkan bagaimana membuat konten artikel yang lebih panjang menggunakan elemen `<article>`.  
Gambar ditampilkan di sisi kiri atau kanan teks menggunakan properti `float`, sedangkan garis horizontal `<hr>` digunakan sebagai pembatas antar artikel.  
Hasil akhirnya berupa tampilan dua artikel dengan layout bergantian (gambar di kiri dan kanan), menyerupai format majalah online.

---

## 9. Tugas Tambahan: Membuat Halaman About dan Contact

### A. Layout Halaman About
Buat file **about.html**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>About - Layout Sederhana</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div id="container">
    <header>
      <h1>Tentang Saya</h1>
    </header>
    <nav>
      <a href="home.html">Home</a>
      <a href="artikel.html">Artikel</a>
      <a href="about.html" class="active">About</a>
      <a href="kontak.html">Kontak</a>
    </nav>
    <section id="main">
      <h2>Profil Singkat</h2>
      <p>Halo! Saya adalah mahasiswa Universitas Pelita Bangsa yang sedang belajar pengembangan web menggunakan HTML dan CSS. Saya memiliki ketertarikan pada desain antarmuka dan pengembangan website yang responsif.</p>
      <h3>Portfolio</h3>
      <ul>
        <li>Website Company Profile</li>
        <li>Aplikasi To-Do List</li>
        <li>Landing Page Produk</li>
      </ul>
    </section>
    <footer>
      <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
  </div>
</body>
</html>
```

Langkah ini bertujuan untuk menambahkan halaman baru bernama **`about.html`**.  
Halaman ini menampilkan informasi tentang penulis atau pemilik website.  
Struktur halaman masih menggunakan layout utama (header, nav, main, footer) agar konsisten.  
Kontennya berisi **profil singkat dan daftar portfolio**.  
Hasil akhirnya adalah halaman “About” yang memberikan informasi tambahan tentang identitas pembuat web.

### B. Layout Halaman Contact
Buat file **kontak.html**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kontak - Layout Sederhana</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div id="container">
    <header>
      <h1>Hubungi Saya</h1>
    </header>
    <nav>
      <a href="home.html">Home</a>
      <a href="artikel.html">Artikel</a>
      <a href="about.html">About</a>
      <a href="kontak.html" class="active">Kontak</a>
    </nav>
    <section id="main">
      <h2>Form Kontak</h2>
      <form action="#" method="post" class="form-contact">
        <label>Nama:</label>
        <input type="text" name="nama" placeholder="Masukkan nama Anda" required>
        <label>Email:</label>
        <input type="email" name="email" placeholder="Masukkan email Anda" required>
        <label>Pesan:</label>
        <textarea name="message" rows="5" placeholder="Tulis pesan Anda..." required></textarea>
        <button type="submit">Kirim</button>
      </form>
    </section>
    <footer>
      <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
  </div>
</body>
</html>
```

Tambahkan CSS berikut pada `style.css`:
```css
/* About & Contact Page */
#main h2 {
  margin-bottom: 15px;
  color: #1f5faa;
}

#main ul {
  list-style-type: square;
  margin-left: 20px;
}

.form-contact {
  display: flex;
  flex-direction: column;
  gap: 10px;
  max-width: 500px;
}

.form-contact input,
.form-contact textarea {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

.form-contact button {
  background-color: #1f5faa;
  color: #fff;
  padding: 10px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
}

.form-contact button:hover {
  background-color: #2b83ea;
}
```

Langkah ini bertujuan agar mahasiswa dapat membuat **formulir kontak sederhana**.  
Halaman baru bernama **`kontak.html`** dibuat dengan elemen `<form>` yang berisi input nama, email, dan pesan.  
Properti CSS seperti `flex-direction: column;` digunakan untuk mengatur tampilan vertikal form.  
Hasil akhirnya adalah halaman “Contact” dengan tampilan bersih dan tombol kirim berwarna biru.

---

## Screenshot
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20103513.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20104113.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20105233.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20105913.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20110143.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20110853.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20111734.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20112119.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20114719.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20145815.png)
![foto](https://github.com/Manueljds2311105/foto/blob/168cbcbf0a866b4ebdf4cec84dd3dc7c3acde30d/Screenshot%202025-10-15%20145840.png)
