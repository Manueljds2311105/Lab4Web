
# Praktikum 4: CSS Layout

## Tujuan
1. Memahami struktur dasar pembuatan layout web.
2. Memahami konsep box element.
3. Menggunakan properti CSS float dan clear.
4. Menggunakan HTML5 semantic elements.
5. Membuat layout web sederhana.

---

## Langkah-langkah Praktikum

### 1. Persiapan Awal
- Buka text editor seperti **VS Code**.
- Buat folder baru bernama `Lab4Web`.
- Pastikan file HTML dapat divalidasi di [validator.w3.org](http://validator.w3.org).

### 2. Membuat File HTML Dasar
Buat file `lab4_box.html`:
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

### 3. Membuat Box Element
Tambahkan:
```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
</section>
```
Menampilkan tiga kotak sejajar.

### 4. Menambahkan CSS Float Property
Tambahkan CSS di `<head>`:
```html
<style>
  div { float: left; padding: 10px; }
  .div1 { background: red; }
  .div2 { background: yellow; }
  .div3 { background: green; }
</style>
```
Kotak akan berjejer ke kiri.

### 5. Mengatur Clearfix (Clear Property)
```html
<div class="div4">Div 4</div>
```
```css
.div4 { background-color: blue; clear: left; float: none; }
```
Div 4 turun ke baris baru.

### 6. Membuat Layout Web Sederhana
Buat folder `lab4_layout`, lalu file `home.html` dan `style.css`.

Isi `home.html`:
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
  <div id="container"></div>
</body>
</html>
```

### 7. Membuat Kerangka Layout
```html
<header><h1>Layout Sederhana</h1></header>
<nav>
  <a href="home.html" class="active">Home</a>
  <a href="artikel.html">Artikel</a>
  <a href="about.html">About</a>
  <a href="kontak.html">Kontak</a>
</nav>
<section id="hero"></section>
<section id="wrapper">
  <section id="main"></section>
  <aside id="sidebar"></aside>
</section>
<footer><p>&copy; 2021 - Universitas Pelita Bangsa</p></footer>
```

### 8. Menambahkan CSS untuk Layout
```css
* { margin: 0; padding: 0; }
body { font-family: 'Open Sans', sans-serif; color: #5a5a5a; }
#container { width: 980px; margin: 0 auto; box-shadow: 0 0 1em #ccc; }
header { padding: 20px; }
nav { background-color: #1f5faa; }
nav a { color: white; padding: 15px 30px; display: inline-block; text-decoration: none; }
```

### 9. Membuat Hero Panel
```html
<section id="hero">
  <h1>Hello World!</h1>
  <p>Deskripsi singkat halaman.</p>
  <a href="#" class="btn">Learn More »</a>
</section>
```
```css
#hero { background-color: #e4e4e5; padding: 50px 20px; margin-bottom: 20px; }
```

### 10. Mengatur Main Content dan Sidebar
```css
#main { float: left; width: 640px; padding: 20px; }
#sidebar { float: left; width: 260px; padding: 20px; }
```

### 11. Membuat Sidebar Widget
Tambahkan widget berisi link dan teks.
```css
.widget-box { border:1px solid #eee; margin-bottom:20px; }
.widget-box .title { background:#428bca; color:#fff; padding:10px; }
.widget-box li a:hover { background-color:#eee; }
```

### 12. Menambahkan Footer
```css
footer { clear: both; background-color: #1d1d1d; color: #eee; padding: 20px; }
```

### 13. Menambahkan Konten Artikel dan Box
Tambahkan elemen `<article>` dan `<div class="box">` berisi gambar dan teks.

### 14. Tugas Akhir
- Tambahkan halaman **About** berisi deskripsi atau portfolio.
- Tambahkan halaman **Contact** berisi form (nama, email, pesan).

---

## 📸 Dokumentasi
Setiap langkah harus disertai **screenshot hasilnya di browser** untuk laporan praktikum.

## 📦 Pengumpulan
1. Buat repository baru bernama `Lab4Web` di GitHub.
2. Commit semua file hasil praktikum.
3. Buat file `README.md` ini di repository.
4. Kirim URL repository ke e-learning kampus.
