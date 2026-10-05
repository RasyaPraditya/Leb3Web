# Leb3Web

# Laporan Praktikum 3: CSS Dasar

## Langkah-Langkah Praktikum

### 1. Membuat Dokumen HTML
* **Penjelasan:** Langkah pertama adalah membuat file `lab2_css_dasar.html` dengan struktur dasar HTML5 yang mencakup bagian `<header>`, `<nav>`, dan konten utama yang dilengkapi ID `intro` serta class `.button`.
* **Screenshot:**
<img width="1920" height="1080" alt="Screenshot (216)" src="https://github.com/user-attachments/assets/be559fe2-8498-4c24-b8d4-044e7b7be88c" />


---

### 2. Mendeklarasikan CSS Internal
* **Penjelasan:** Menambahkan aturan styling menggunakan tag `<style>` di dalam bagian `<head>` dokumen. CSS Internal ini mengatur jenis font dasar (`body`), batas bawah header (`header`), serta ukuran dan warna judul (`h1`).
* **Screenshot:**
<img width="1920" height="1080" alt="Screenshot (217)" src="https://github.com/user-attachments/assets/6e62c6a0-7788-41e9-8477-554af37d42dc" />


---

### 3. Menambahkan Inline CSS
* **Penjelasan:** Menambahkan atribut `style` langsung pada tag `<p>` di dalam elemen HTML untuk memberikan instruksi styling secara spesifik pada baris kode tersebut (misalnya mengatur rata tengah dan warna teks).
* **Screenshot:**
<img width="1920" height="1080" alt="Screenshot (218)" src="https://github.com/user-attachments/assets/64ff813a-1c1a-447f-95ac-84134765d94a" />


---

### 4. Membuat CSS Eksternal
* **Penjelasan:** Membuat file baru bernama `style_eksternal.css` lalu menghubungkannya ke dokumen HTML menggunakan tag `<link rel="stylesheet" href="style_eksternal.css">` pada bagian `<head>`. Aturan CSS eksternal ini mengatur tampilan navigasi (`nav`).
* **Screenshot:**
<img width="1920" height="1080" alt="Screenshot (219)" src="https://github.com/user-attachments/assets/e5e20724-27e2-45e1-b131-921520f4861d" />


---

### 5. Menambahkan CSS Selector (ID dan Class Selector)
* **Penjelasan:** Menambahkan styling lebih rinci menggunakan ID Selector (`#intro`, `#intro h1`) dan Class Selector (`.button`, `.btn-primary`) pada file `style_eksternal.css` untuk mengatur latar belakang, border, padding, serta tombol.
* **Screenshot:**
<img width="1920" height="1080" alt="Screenshot (224)" src="https://github.com/user-attachments/assets/66a32aa9-7cff-4d7d-a35f-6bc91002ab0c" />


---

# Jawaban Tugas Praktikum 3 - CSS Dasar


### 1. Eksperimen Properti CSS
Eksperimen dilakukan dengan menambah dan mengubah beberapa properti CSS dasar seperti `color`, `background-color`, `font-size`, `margin`, `padding`, dan `border` berdasarkan referensi *CSS Cheat Sheet*.

---

### 2. Perbedaan Pendeklarasian `h1 {...}` dengan `#intro h1 {...}`

* `h1 {...}` *(Element/Tag Selector)* : Mengaplikasikan gaya CSS ke **seluruh** elemen `<h1>` yang ada di dalam dokumen HTML. Memiliki tingkat spesifisitas (*specificity*) yang rendah.
* `#intro h1 {...}` *(Descendant Selector dengan ID)* : Hanya mengaplikasikan gaya CSS ke elemen `<h1>` yang berada **di dalam** elemen dengan `id="intro"`. Memiliki tingkat spesifisitas yang lebih tinggi karena menggunakan ID.

---

### 3. Hierarki Tampilan Antara Internal CSS, External CSS, dan Inline CSS

Jika sebuah elemen dideklarasikan menggunakan Internal CSS, External CSS, dan Inline CSS sekaligus, maka deklarasi yang akan ditampilkan oleh *browser* adalah **Inline CSS** karena memiliki prioritas (*specificity*) paling tinggi.

**Urutan Prioritas (Cascade):**
1. **Inline CSS** *(Prioritas Tertinggi)*
2. **Internal CSS** dan **External CSS** *(Memiliki bobot yang sama, sehingga yang berlaku adalah deklarasi yang ditulis atau dipanggil paling terakhir)*

**Contoh Kode:**

`<head>`
  `<!-- External CSS -->`
  `<link rel="stylesheet" href="style.css">`
  `<!-- Misal isi style.css: p { color: blue; } -->`

  `<!-- Internal CSS -->`
  `<style>`
    `p { color: green; }`
  `</style>`
`</head>`
`<body>`
  `<!-- Inline CSS -->`
  `<p style="color: red;">Teks ini akan berwarna MERAH.</p>`
`</body>`

*Penjelasan:* Teks di atas akan ditampilkan berwarna **merah** karena diset secara langsung menggunakan *Inline CSS* (`style="color: red;"`).

---

### 4. Prioritas Antara Selector ID dan Class

Jika pada sebuah elemen HTML terdapat ID dan Class sekaligus (`<p id="paragraf-1" class="text-paragraf">`), maka deklarasi CSS yang akan ditampilkan oleh *browser* adalah **Selector ID (`#paragraf-1`)**. Hal ini disebabkan Selector ID memiliki nilai spesifisitas (*specificity*) yang lebih tinggi daripada Class Selector.

**Contoh Kode:**

**CSS:**
`/* Selector ID (Spesifisitas Tinggi) */`
`#paragraf-1 {`
  `color: blue;`
  `font-weight: bold;`
`}`

`/* Selector Class (Spesifisitas Rendah) */`
`.text-paragraf {`
  `color: red;`
  `font-weight: normal;`
`}`

**HTML:**
`<p id="paragraf-1" class="text-paragraf">Teks Paragraf Contoh</p>`

*Penjelasan:* Teks di atas akan ditampilkan berwarna **biru** dan cetak **tebal** (*bold*) karena aturan gaya dari `#paragraf-1` (ID) mengalahkan aturan dari `.text-paragraf` (Class).
