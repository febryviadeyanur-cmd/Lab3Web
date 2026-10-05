# Lab3Web - Praktikum 3 CSS Dasar

Repository ini berisi hasil pengerjaan Praktikum 3 mata kuliah Pemrograman Web, dengan topik CSS Dasar (Internal, Inline, Eksternal, dan CSS Selector).

**Dosen Pengampu:** Agung Nugroho
**Mata Kuliah:** Pemrograman Web
**Praktikum:** Praktikum 3 - CSS Dasar

## Tujuan Praktikum

1. Memahami konsep dasar CSS.
2. Memahami aturan penulisan CSS.
3. Memahami selector sebagai pengontrol CSS.
4. Membuat pengaturan CSS pada HTML.

## Struktur File

```text
Lab3Web/
├── lab2_css_dasar.html
├── style_eksternal.css
├── screenshots/
└── README.md
```

## Langkah Praktikum

### 1. Membuat Dokumen HTML

Pada langkah pertama dibuat file `lab2_css_dasar.html` dengan struktur dasar HTML.

Membuat struktur dasar HTML dengan `<header>`, `<nav>`, dan `<div id="intro">` yang berisi heading `Hello World`, paragraf deskripsi, serta sebuah tombol link.

Hasil tampilan awal:

![alt text](<image 1.png>)

### 2. CSS Internal

Selanjutnya ditambahkan CSS internal menggunakan tag `<style>` pada bagian `<head>`.

CSS digunakan untuk mengatur font pada halaman, tampilan header, ukuran dan warna heading, serta warna tulisan yang menggunakan tag `<i>`.

Menambahkan tag `<style>` pada bagian `<head>` dokumen untuk mengatur:
- `body` → font menggunakan `Open Sans`
- `header` → tinggi minimum dan garis bawah
- `h1` → ukuran, warna, perataan teks, dan padding
- `h1 i` → warna khusus untuk teks miring di dalam `h1`.

CSS yang dikerjakan:

```css
body {
    font-family: 'Open Sans', sans-serif;
}

header {
    min-height: 80px;
    border-bottom: 1px solid #77CCEF;
}

h1 {
    font-size: 24px;
    color: #0F189F;
    text-align: center;
    padding: 20px 10px;
}

h1 i {
    color: #6d6a6b;
}
```

Hasil setelah ditambahkan CSS internal:

![alt text](<image 3.png>)

Hasil yang sudah di rapihkan:

![alt text](<image 2.png>)

### 3. Inline CSS

Pada langkah ini ditambahkan CSS langsung pada tag HTML menggunakan atribut `style`.

```html
<p style="text-align: center; color: #ccd8e4;">
```

CSS digunakan untuk mengatur posisi teks menjadi rata tengah dan mengubah warna teks.

![alt text](<image 3.png>)

Hasil setelah ditambahkan Inline CSS:

![alt text](<image 4.png>)

### 4. CSS Eksternal

Selanjutnya dibuat file CSS baru dengan nama `style_eksternal.css`.

Membuat file terpisah `style_eksternal.css` berisi deklarasi untuk elemen `nav` dan `nav a`, lalu menghubungkannya ke dokumen HTML menggunakan tag `<link>`pada bagian `<head>`.

```html
<link rel="stylesheet" href="style_eksternal.css" type="text/css">
```

Dengan menggunakan CSS eksternal, kode CSS dipisahkan dari file HTML.

Hasil setelah CSS eksternal digunakan:

![alt text](<image 5.png>)

### 5. CSS Selector

Pada langkah terakhir ditambahkan CSS Selector menggunakan selector elemen, ID, dan class.

Beberapa selector yang digunakan adalah `nav`, `nav a`, `#intro`, `#intro h1`, `.button`, dan `.btn-primary`.

Menambahkan deklarasi `#intro`, `#intro h1`, `.button`, dan `.btn-primary` pada file `style_eksternal.css` untuk mengatur tampilan elemen berdasarkan ID dan Class.

CSS yang dikerjakan:

```css
#intro {
    background: #418fb1;
    border: 1px solid #099249;
    min-height: 100px;
    padding: 10px;
}

#intro h1 {
    text-align: left;
    border: 0;
    color: #fff;
}

.button {
    padding: 15px 20px;
    background: #bebcbd;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
}
```

Hasil akhir praktikum:

![alt text](<image 6.png>)

---

## Jawaban Pertanyaan

### 1. Eksperimen Properti dan Nilai CSS

Lakukan eksperimen dengan mengubah dan menambah properti dan nilai pada kode CSS dengan mengacu pada CSS Cheat Sheet yang diberikan pada file terpisah dari modul ini.

jawaban:

Pada bagian ini dilakukan percobaan dengan mengubah beberapa properti dan nilai CSS untuk melihat perubahan pada tampilan halaman.

Properti yang digunakan antara lain `font-family`, `font-size`, `color`, `background`, `padding`, `margin`, `border`, dan `text-align`.

Dari percobaan dapat dilihat bahwa perubahan nilai CSS dapat mengubah tampilan elemen HTML.

Hasil dari percobaan:

![alt text](Percobaan_1.png)

### 2. Perbedaan `h1 {...}` dengan `#intro h1 {...}`

Apa perbedaan pendeklarasian CSS elemen h1 {...} dengan #intro h1 {...}? Berikan penjelasannya!

jawaban:

`h1 {...}` adalah *element selector*, berlaku untuk semua tag `<h1>` di seluruh halaman tanpa terkecuali. Sedangkan `#intro h1 {...}` adalah *descendant selector* (gabungan ID dan elemen), yang berlaku untuk `<h1>` yang berada di dalam elemen ber-`id="intro"`. Karena menunjukkan ID, `#intro h1` memiliki specificity lebih tinggi dibanding `h1` biasa, sehingga aturan yang akan menang jika keduanya menarget elemen `<h1>` yang sama di dalam `#intro`.

Kesimpulannya:

`h1 {...}` digunakan untuk mengatur semua elemen `<h1>` yang ada pada halaman. Sedangkan `#intro h1 {...}` digunakan untuk mengatur elemen `<h1>` yang berada di dalam elemen dengan `id="intro"`.

Jadi, `#intro h1` lebih khusus karena hanya berlaku untuk `<h1>` yang berada di dalam `#intro`.


### 3. Internal, Eksternal, dan Inline CSS

Apabila ada deklarasi CSS secara internal, lalu ditambahkan CSS eksternal dan inline CSS pada elemen yang sama. Deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya!

jawaban:

Jika sebuah elemen menggunakan CSS internal, eksternal, dan inline pada properti yang sama, maka Inline CSS memiliki prioritas lebih tinggi.

Urutan prioritas CSS dari yang paling lemah ke paling kuat:
 
1. External CSS
2. Internal CSS
3. Inline CSS

Contohnya:

```html
<p style="color: red;">Teks ini</p>
```

Jika terdapat CSS yang mengatur warna paragraf menjadi biru, warna yang digunakan pada paragraf tetap merah karena menggunakan Inline CSS.

Untuk CSS internal dan eksternal, jika selector dan tingkat prioritasnya sama, deklarasi yang ditulis lebih akhir akan digunakan.

Jika hanya internal vs eksternal (tanpa inline) dengan selector yang sama, maka yang menang adalah deklarasi yang ditulis/dimuat paling belakangan dalam dokumen HTML.

### 4. ID dan Class Selector

Pada sebuah elemen HTML terdapat ID dan Class, apabila masing-masing selector tersebut terdapat deklarasi CSS, maka deklarasi manakah yang akan ditampilkan pada browser? Berikan penjelasan dan contohnya! (<p id="paragraf-1" class="text-paragraf">)

jawaban:

Jika satu elemen memiliki ID dan Class, ID Selector memiliki prioritas yang lebih tinggi dibandingkan Class Selector.

Contohnya:

```html
<p id="paragraf-1" class="text-paragraf">
    Contoh teks
</p>
```

```css
#paragraf-1 {
    color: blue;
}

.text-paragraf {
    color: red;
}
```

Hasilnya teks akan berwarna biru karena `#paragraf-1` merupakan ID Selector dan memiliki prioritas lebih tinggi daripada `.text-paragraf`.

Browser akan menampilkan warna **biru**, karena ID selector memiliki specificity lebih tinggi daripada class selector. Urutan specificity CSS secara umum: inline style > ID selector > class/attribute/pseudo-class selector > element selector. Jadi ID tetap menang meskipun class ditulis setelah ID dalam kode CSS.

## Hasil Validasi CSS
 
File `style_eksternal.css` telah divalidasi melalui [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) dengan hasil:
 
> **Congratulations! No Error Found.**
 
Validasi dilakukan dengan cara mengunggah file `style_eksternal.css` ke W3C CSS Validator (mode *By file upload*), kemudian menjalankan pengecekan (*Check*). Hasil validasi menunjukkan bahwa penulisan CSS sudah sesuai standar W3C dan tidak ditemukan error pada seluruh deklarasi (selector `nav`, `#intro`, `.button`, `.btn-primary`, dsb).
 
**Screenshot hasil validasi:**

Validasi CSS:

![alt text](<validasi css.png>)

Validasi Style eksternal

![alt text](<validasi style.png>)

## Kesimpulan

Pada praktikum ini dipelajari cara menggunakan CSS pada HTML, yaitu melalui CSS internal, inline, dan eksternal.

Selain itu juga dipelajari penggunaan CSS Selector seperti selector elemen, ID, dan class untuk mengatur tampilan halaman web.