# 🌐 Praktikum 4 - CSS Layout

## 📘 Tujuan
Praktikum ini bertujuan agar mahasiswa memahami konsep dasar pembuatan layout web menggunakan **HTML dan CSS**, meliputi:
1. Struktur dasar pembuatan layout web.  
2. Konsep box element pada HTML.  
3. Penggunaan properti `float` dan `clear` dalam CSS.  
4. Penerapan elemen semantik HTML5.  
5. Pembuatan layout web sederhana menggunakan HTML dan CSS.

---

## 🧩 1. Persiapan
Langkah awal:
- Buka text editor (misalnya VS Code).
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

---

## 📦 2. Membuat Box Element
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

📷 **Hasil:**
Tiga kotak sejajar secara horizontal dengan warna merah, kuning, dan hijau.

---

## 🧱 3. Menambahkan Clearfix
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

📷 **Hasil:**
Kotak biru muncul di bawah tiga kotak pertama karena efek `clear: left`.

---

## 🧭 4. Membuat Layout Web Sederhana
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

---

## 🎨 5. Menambahkan Style (style.css)
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

📷 **Hasil:**  
Tampilan web sederhana dengan header, navigasi, hero section, sidebar, main content, dan footer.

---

## 🧰 6. Menambahkan Widget Sidebar
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

📷 **Hasil:**  
Sidebar berisi daftar link dengan tampilan kotak (widget).

---

## 🧾 7. Menambahkan Konten di Main Section
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

📷 **Hasil:**  
Tiga kolom konten sejajar dengan gambar berbentuk lingkaran.

---

## 📰 8. Menambahkan Artikel
Tambahkan konten artikel di bawah main:
```html
<hr class="divider" />
<article class="entry">
  <h2>Featurette Heading</h2>
  <img src="https://dummyimage.com/150/7b8a70/fff.png" alt="">
  <p>Lorem ipsum dolor sit amet...</p>
</article>
```

📷 **Hasil:**  
Tampilan artikel dengan gambar di sisi kiri/kanan dan teks di sampingnya.

---

## 🧩 9. Tugas Tambahan: Membuat Halaman About dan Contact

### 🧑‍💼 A. Layout Halaman About
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

### 💌 B. Layout Halaman Contact
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

📷 **Hasil:**  
- Halaman **About** menampilkan deskripsi dan portfolio.  
- Halaman **Contact** menampilkan form input nama, email, dan pesan.

---

## ✨ Kesimpulan
Dalam praktikum ini dipelajari:
- Cara membuat layout web menggunakan **box element** dan **float**.  
- Penggunaan **elemen semantik HTML5** seperti `<header>`, `<nav>`, `<section>`, `<aside>`, dan `<footer>`.  
- Cara mengatur posisi elemen dengan **CSS layout** untuk menghasilkan tampilan web yang terstruktur dan responsif.  
- Pembuatan halaman tambahan seperti **About** dan **Contact** menggunakan layout yang konsisten.

---

**🧑‍💻 Dibuat oleh:**  
_Nama Mahasiswa_  
**NIM:** _Isi dengan NIM kamu_  
**Mata Kuliah:** Pemrograman Web  
**Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom._  
