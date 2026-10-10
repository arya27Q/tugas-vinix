# Log Penggunaan AI - Halaman Katalog Surplus

## Tahap 1: Setup Header & Layout Utama

**Prompt:**

> "Bertindaklah sebagai Ahli HTML5 Semantik. Buatkan kerangka untuk halaman Katalog (katalog.html) dengan ATURAN KETAT: TANPA CSS, tanpa div-soup. Buat `<header>` yang identik dengan halaman dashboard, namun menu 'Katalog' di `<nav>` dibuat `<strong>`. Setelah `<header>`, buat elemen `<main>`. Di dalam `<main>`, buat sebuah `<aside>` untuk area Filter di sebelah kiri, dan sebuah `<section>` untuk daftar makanan di sebelah kanan."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Katalog Surplus - PlusFood</title>
</head>
<body>
    <div class="header-container">
        <header>
            <div class="logo-wrapper">
                <a href="index.html">
                    <img src="../../../assets/images/plusfood-icon.png" alt="Logo PlusFood">
                    <p>PlusFood - Food Rescue Kampus</p>
                </a>
            </div>
            <div class="nav-wrapper">
                <nav>
                    <ul>
                        <li><a href="index.html">Beranda</a></li>
                        <li><a href="katalog.html"><strong>Katalog</strong></a></li>
                        <li><a href="riwayat.html">Riwayat</a></li>
                    </ul>
                </nav>
            </div>
            <div class="user-actions">
                <a href="notifikasi.html" title="Notifikasi">🔔</a>
                <a href="profil.html" title="Profil Raka">R</a>
            </div>
        </header>
    </div>

    <div class="main-container">
        <main>
            <div class="sidebar">
                <aside>
                    <!-- Isi filter di sini -->
                </aside>
            </div>
            <div class="content">
                <section>
                    <!-- Isi daftar katalog di sini -->
                </section>
            </div>
        </main>
    </div>
</body>
</html>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Katalog Surplus - PlusFood</title>
</head>
<body>
    <header>
        <a href="index.html">
            <img src="../../../assets/images/plusfood-icon.png" alt="Logo PlusFood">
            <p>PlusFood - Food Rescue Kampus</p>
        </a>
        <nav>
            <ul>
                <li><a href="index.html">Beranda</a></li>
                <li><a href="katalog.html"><strong>Katalog</strong></a></li>
                <li><a href="riwayat.html">Riwayat</a></li>
            </ul>
        </nav>
        <form action="search_results.html" method="get">
            <input type="search" name="q" placeholder="Cari makanan surplus..." required>
            <button type="submit">Cari</button>
        </form>
        <a href="notifikasi.html" title="Notifikasi">🔔</a>
        <a href="profil.html" title="Profil Raka">R</a>
    </header>

    <main>
        <aside>
            <!-- Isi filter di sini -->
        </aside>
        
        <section>
            <!-- Isi daftar katalog di sini -->
        </section>
    </main>
</body>
</html>
```

---

## Tahap 2: Form Filter (Aside)

**Prompt:**

> "Di dalam elemen `<aside>`, tambahkan form filter. Buat `<h2>` 'Filter' dan tautan 'Reset'. Buat `<form>` dengan beberapa `<fieldset>`. Fieldset pertama untuk 'Rentang Harga' (gunakan `<input type="range">`). Fieldset kedua 'Kategori' berisi input tipe radio. Fieldset ketiga 'Jarak dari Kampus'. Fieldset keempat 'Jendela Jam Ambil (Malam)'. Fieldset kelima 'Jaminan & Keamanan' dengan beberapa checkbox (Mitra terverifikasi, Dimasak hari ini, dll). Terakhir tambahkan `<button type="submit">` 'Terapkan - 18 hasil'."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="aside-wrapper">
            <aside>
                <div class="filter-header">
                    <h2>Filter</h2>
                    <a href="katalog.html">Reset</a>
                </div>

                <div class="filter-form-container">
                    <form action="katalog.html" method="get">
                        <div class="fieldset-group">
                            <fieldset>
                                <legend>Rentang Harga</legend>
                                <input type="range" id="harga" name="harga" min="5000" max="25000" step="1000" value="15000">
                                <p><small>Rp5.000 - Rp15.000 - Rp25.000</small></p>
                            </fieldset>
                        </div>

                        <div class="fieldset-group">
                            <fieldset>
                                <legend>Kategori</legend>
                                <label><input type="radio" name="kategori" value="nasi"> Nasi</label>
                                <label><input type="radio" name="kategori" value="semua" checked> Semua</label>
                            </fieldset>
                        </div>

                        <div class="button-wrapper">
                            <button type="submit">Terapkan &middot; 18 hasil</button>
                        </div>
                    </form>
                </div>
            </aside>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <aside>
            <header>
                <h2>Filter</h2>
                <a href="katalog.html">Reset</a>
            </header>

            <form action="katalog.html" method="get">
                <fieldset>
                    <legend>Rentang Harga</legend>
                    <input type="range" id="harga" name="harga" min="5000" max="25000" step="1000" value="15000">
                    <p><small>Rp5.000 - Rp15.000 - Rp25.000</small></p>
                </fieldset>

                <fieldset>
                    <legend>Kategori</legend>
                    <label><input type="radio" name="kategori" value="nasi"> Nasi</label>
                    <label><input type="radio" name="kategori" value="mie"> Mie</label>
                    <label><input type="radio" name="kategori" value="semua" checked> Semua</label>
                </fieldset>

                <!-- Fieldset lainnya ditambahkan tanpa div -->

                <button type="submit">Terapkan &middot; 18 hasil</button>
            </form>
        </aside>
```

---

## Tahap 3: Daftar Katalog (Section Utama)

**Prompt:**

> "Di dalam `<section>` sebelah kanan, tambahkan `<header>` dengan `<h1>` 'Katalog Surplus', deskripsi `<p>` '18 hasil - di bawah Rp15.000 - ≤ 30 menit', dan tombol 'Urutkan: Terdekat'. Kemudian tambahkan 6 elemen `<article>` yang merepresentasikan kartu makanan. Setiap `<article>` wajib memiliki `<img>`, `<mark>` diskon, `<button>` favorit, `<p><small>` nama warung, `<h3>` nama makanan, `<p>` harga pakai `<del>` untuk harga asli, dan `<p><small>` jarak serta sisa porsi. Sesuaikan isi teks dan gambarnya dengan desain."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="catalog-section">
            <section>
                <div class="catalog-header">
                    <header>
                        <h1>Katalog Surplus</h1>
                        <p>18 hasil &middot; di bawah Rp15.000 &middot; &le; 30 menit</p>
                        <button type="button">Urutkan: Terdekat</button>
                    </header>
                </div>

                <div class="product-grid">
                    <div class="card">
                        <article>
                            <div class="badge"><mark>Diskon 52%</mark></div>
                            <button type="button" title="Simpan ke favorit">&hearts;</button>
                            <div class="image-wrapper">
                                <img src="../../../assets/images/nasi-ayam-bakar.png" alt="Seporsi Nasi Ayam Bakar">
                            </div>
                            <div class="text-wrapper">
                                <p><small>Warung Bu Sari</small></p>
                                <h3>Nasi Ayam Bakar</h3>
                                <p><strong>Rp12.000</strong> <del>Rp25.000</del></p>
                                <p><small>2 km &middot; Sisa 3 porsi</small></p>
                            </div>
                        </article>
                    </div>

                    <!-- 5 Kartu produk lainnya -->
                </div>
            </section>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <header>
                <h1>Katalog Surplus</h1>
                <p>18 hasil &middot; di bawah Rp15.000 &middot; &le; 30 menit</p>
                <button type="button">Urutkan: Terdekat</button>
            </header>

            <article>
                <mark>Diskon 52%</mark>
                <button type="button" title="Simpan ke favorit">&hearts;</button>
                <img src="../../../assets/images/nasi-ayam-bakar.png" alt="Seporsi Nasi Ayam Bakar">
                <p><small>Warung Bu Sari</small></p>
                <h3>Nasi Ayam Bakar</h3>
                <p><strong>Rp12.000</strong> <del>Rp25.000</del></p>
                <p><small>2 km &middot; Sisa 3 porsi</small></p>
            </article>

            <article>
                <mark>Diskon 54%</mark>
                <button type="button" title="Simpan ke favorit">&hearts;</button>
                <img src="../../../assets/images/nasi-campur-bali.png" alt="Seporsi Nasi Campur Bali">
                <p><small>Dapur Mbak Ayu</small></p>
                <h3>Nasi Campur Bali</h3>
                <p><strong>Rp13.000</strong> <del>Rp28.000</del></p>
                <p><small>1,2 km &middot; Sisa 5 porsi</small></p>
            </article>

            <!-- Kartu produk lainnya dilanjutkan murni tanpa div -->
        </section>
```

---

# Log Penggunaan AI - Halaman Detail Produk & Riwayat Pesanan

## Halaman Detail Produk

### Tahap 1: Layout Utama & Banner
**Prompt:**

> "Bertindaklah sebagai Ahli HTML5 Semantik. Buatkan kerangka untuk halaman Detail Produk (detail_makanan.html) berdasarkan desain yang diberikan. Aturan paling ketat: TANPA CSS, tanpa satupun div-soup. Gunakan tag `<header>` untuk navigasi atas (tombol kembali, label diskon, tombol favorit) dan informasi batch masak. Lalu, siapkan `<main>` sebagai kontainer utama halaman ini."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="main-wrapper">
    <div class="header-banner">
        <!-- header content -->
    </div>
    <main>
        <!-- Konten di dalam main -->
    </main>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <header>
        <nav>
            <a href="index.html">&larr; Kembali</a>
            <strong>Diskon 52%</strong>
            <strong>Verified Kitchen Kampus Unesa</strong>
            <button type="button" title="Favorit">&hearts;</button>
        </nav>
        
        <ul>
            <li>Batch Masak: 16.30 WIB</li>
            <li>Food Warmer Grade A</li>
            <li>Penyelamatan Emisi: 0,85 kg CO2e</li>
        </ul>
    </header>

    <main>
        <!-- Konten Detail Produk dan Reservasi -->
    </main>
```

### Tahap 2: Informasi Makanan (Section Kiri)
**Prompt:**

> "Di dalam `<main>`, buat `<section>` untuk informasi makanan di bagian kiri. Buat `<header>` di dalamnya untuk `<h1>` (judul makanan), tag label siap santap, dan info warung. Selanjutnya tambahkan beberapa `<article>` dan `<aside>` untuk mendeskripsikan harga coret, ketersediaan porsi, jadwal & alamat pengambilan, deksripsi makanan, komposisi menu, dan profil singkat warung. Pastikan semua elemen seperti daftar (`<ul>`/`<li>`), judul (`<h2>`/`<h3>`), dan teks kecil (`<small>`) tersusun rapi menggunakan semantik yang tepat tanpa membungkusnya dengan `<div>`."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="left-section">
            <section>
                <div class="header-info">
                    <header>
                        <h1>Nasi Ayam Bakar Bumbu Rujak Spesial</h1>
                        <mark>Menu Siap Santap Malam</mark>
                    </header>
                </div>
                <div class="price-container">
                    <!-- detail div soup -->
                </div>
            </section>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <header>
                <h1>Nasi Ayam Bakar Bumbu Rujak Spesial</h1>
                <strong>Menu Siap Santap Malam</strong>
                <p>Warung Bu Sari &middot; &starf; 4.8 (148 ulasan) &middot; <strong>Higienis &amp; Halal</strong></p>
            </header>

            <article>
                <p><del>Rp25.000</del></p>
                <h2>Rp12.000</h2>
                <strong>Hemat 52%</strong>
            </article>

            <aside>
                <p><strong>&Delta; Sisa 3 porsi</strong></p>
                <p><small>Segera reservasi sebelum habis</small></p>
                <strong>Cepat Habis</strong>
            </aside>

            <ul>
                <li>
                    <h3>Jadwal Pengambilan</h3>
                    <p><strong>19.30 &ndash; 20.30 WIB</strong></p>
                    <p><small>Hari ini - tutup 21.00 WIB</small></p>
                </li>
                <li>
                    <h3>Alamat Ambil</h3>
                    <p><strong>Jl. Ketintang Baru No. 12</strong></p>
                    <p><small>1,2 km dari Kampus Unesa</small></p>
                </li>
                <li>
                    <h3>Wadah Ramah Lingkungan</h3>
                    <p><small>Bawa wadah sendiri untuk poin green rescue, atau pakai kotak warung tanpa biaya.</small></p>
                </li>
            </ul>

            <article>
                <h2>Deskripsi Makanan</h2>
                <p>Ayam bakar bumbu rujak gurih-manis, dimasak pukul 16.30 dan disimpan hangat di food warmer. Siap disantap malam ini.</p>
            </article>

            <article>
                <h2>Komposisi Paket Menu</h2>
                <ul>
                    <li>1 Porsi Nasi Putih Pulen</li>
                    <li>1 Potong Paha/Dada Bakar Rujak</li>
                    <li>Sambal Terasi Segar Matang</li>
                    <li>Lalapan Timun &amp; Kemangi</li>
                    <li>Tempe Goreng Crispy</li>
                </ul>
            </article>

            <aside>
                <p><strong>BS</strong></p>
                <h3>Warung Bu Sari</h3>
                <strong>Mitra Aktif Unesa</strong>
                <p><small>Bergabung sejak Maret 2023 &middot; 1.420+ porsi diselamatkan</small></p>
                <a href="profil_warung.html">Kunjungi Profil Warung</a>
            </aside>
        </section>
```

### Tahap 3: Ringkasan Reservasi (Aside Kanan)
**Prompt:**

> "Di sebelah kanan informasi makanan tadi (masih di dalam `<main>`), tambahkan `<aside>` untuk ringkasan reservasi pemesanan. Gunakan `<section>` di dalamnya yang memuat form aksi `<form action="pembayaran.html">`. Dalam form tersebut sediakan elemen kontrol `<fieldset>` dan input bertipe angka untuk menentukan jumlah porsi, rincian detail harga (termasuk diskon subsidi surplus), total bayar, serta tombol submit 'Reservasi Sekarang'. Jangan lupa sisipkan informasi aturan food rescue kampus di luar form."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="right-sidebar">
            <aside>
                <div class="reservation-box">
                    <section>
                        <header>
                            <h2>Ringkasan Reservasi</h2>
                        </header>
                        <div class="form-wrapper">
                            <!-- form div soup -->
                        </div>
                    </section>
                </div>
            </aside>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <aside>
            <section>
                <header>
                    <h2>Ringkasan Reservasi</h2>
                    <strong>1 Tiket / Pesanan</strong>
                </header>

                <form action="pembayaran.html" method="post">
                    <fieldset>
                        <label for="jumlah">Jumlah Porsi</label>
                        <button type="button">-</button>
                        <input type="number" id="jumlah" name="jumlah" value="1" min="1" max="3" readonly>
                        <button type="button">+</button>
                    </fieldset>

                    <p><strong>Anda menghemat emisi karbon setara 1,2 kg CO2e!</strong></p>

                    <ul>
                        <li>Harga Normal Porsi (x1): Rp25.000</li>
                        <li>Subsidi Surplus Pangan: -Rp13.000</li>
                        <li>Biaya Layanan: GRATIS</li>
                    </ul>

                    <p>TOTAL PEMBAYARAN</p>
                    <h2>Rp12.000</h2>
                    <strong>QRIS / Tunai</strong>

                    <button type="submit">Reservasi Sekarang &rarr;</button>
                    <p><small>Konfirmasi instan via Barcode Kampus</small></p>
                </form>
            </section>

            <section>
                <h3>Aturan Food Rescue Unesa</h3>
                <p><small>Tunjukkan kode pemesanan kepada staf Warung Bu Sari saat mengambil makanan pukul 19.30 &ndash; 20.30 WIB.</small></p>
            </section>
        </aside>
```

---

## Halaman Riwayat Pesanan

### Tahap 1: Header & Statistik Dampak
**Prompt:**

> "Buatkan kerangka halaman Riwayat Pesanan (riwayat_pesanan.html) dengan semantik murni HTML5. Di dalam elemen `<main>`, mulailah dengan membuat `<header>` halaman yang memuat judul utama. Selanjutnya, buat `<section>` khusus untuk menampilkan statistik dampak penyelamatan pangan yang telah dilakukan mahasiswa. Susun statistiknya (Porsi makanan, Uang dihemat, Emisi dicegah) ke dalam blok-blok `<article>` yang berdampingan, tanpa menggunakan satupun pembungkus div."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
    <div class="main-content">
        <main>
            <div class="page-header">
                <header>
                    <h1>Riwayat Reservasi Makanan</h1>
                </header>
            </div>
            
            <div class="stats-container">
                <section>
                    <div class="stat-card">
                        <article>
                            <h3>Porsi Makanan</h3>
                            <h2>8 Porsi</h2>
                        </article>
                    </div>
                </section>
            </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <main>
        <header>
            <p><mark>DAMPAK PENYELAMATAN PANGAN</mark></p>
            <h1>Riwayat Reservasi Makanan</h1>
        </header>

        <section>
            <article>
                <h3>Porsi Makanan</h3>
                <h2>8 Porsi</h2>
                <p><small>Penyelamatan berhasil</small></p>
            </article>
            <article>
                <h3>Total Uang Dihemat</h3>
                <h2>Rp98.000</h2>
                <p><small>Dari subsidi surplus</small></p>
            </article>
            <article>
                <h3>Emisi Karbon Dicegah</h3>
                <h2>3,4 kg</h2>
                <p><small>Setara menanam 1 pohon</small></p>
            </article>
        </section>
```

### Tahap 2: Navigasi Status & Daftar Riwayat
**Prompt:**

> "Tepat setelah section statistik, tambahkan sebuah `<nav>` menu tab untuk memfilter status pesanan (Pesanan Aktif, Selesai Diambil, Dibatalkan). Lalu, buat `<section>` daftar riwayat pesanan, di mana tiap riwayat pesanan adalah komponen mandiri dalam `<article>`. Cantumkan keterangan jam selesai, gambar pesanan, nama warung, dan harga akhir dengan jelas di dalam `<article>` tersebut."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
            <div class="tabs-menu">
                <nav>...</nav>
            </div>
            <div class="history-list">
                <section>
                    <div class="history-item">
                        <!-- item konten -->
                    </div>
                </section>
            </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <nav>
            <ul>
                <li><a href="riwayat_aktif.html">Pesanan Aktif (1)</a></li>
                <li><a href="riwayat_selesai.html"><strong>Selesai Diambil</strong></a></li>
                <li><a href="riwayat_batal.html">Dibatalkan</a></li>
            </ul>
        </nav>

        <section>
            <article>
                <header>
                    <mark>Selesai Diambil</mark>
                    <p><small>Kemarin, 23 Okt 2026 &middot; 20.15 WIB</small></p>
                </header>
                <img src="../../../assets/images/nasi-ayam-bakar.png" alt="Paket Nasi Ayam Bakar Bumbu Rujak Spesial">
                
                <h3>Warung Bu Sari Ketintang</h3>
                <p>Nasi Ayam Bakar Bumbu Rujak Spesial (x1)</p>
                <p><strong>Rp12.000</strong></p>
                <a href="detail_pesanan.html">Lihat Detail Pesanan</a>
            </article>
        </section>
```

### Tahap 3: Banner Edukasi
**Prompt:**

> "Akhiri struktur `<main>` di halaman riwayat pesanan dengan sebuah `<aside>` berisi banner edukasi, yang mengajak pengguna (mahasiswa) membagikan pengalaman penyelamatan pangan mereka ke media sosial."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
            <div class="education-banner">
                <aside>
                    <div class="banner-content">
                        <!-- konten -->
                    </div>
                </aside>
            </div>
        </main>
    </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <aside>
            <h2>Bantu Sebarkan Kebaikan</h2>
            <p>Bagikan pengalaman penyelamatan panganmu ke media sosial untuk inspirasi mahasiswa lain!</p>
            <button type="button">Bagikan ke Instagram Story</button>
        </aside>
    </main>
```

---

## Halaman Checkout & Sukses

### Tahap 1: Layout & Navigasi Checkout
**Prompt:**

> "Sekarang kita kerjakan halaman Checkout (checkout.html). Aturan yang sama: HTML5 semantik ketat tanpa div-soup. Buat `<header>` di dalam `<main>` untuk judul 'Checkout Reservasi'. Setelah judul, sediakan elemen `<nav>` menggunakan ordered list (`<ol>`) yang berfungsi sebagai breadcrumb/progress bar checkout (misalnya langkah Detail, Data Diri, Pembayaran)."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="checkout-page">
    <div class="main-container">
        <main>
            <div class="checkout-header">
                <header>...</header>
            </div>
            <div class="checkout-nav">
                <nav>
                    <ul>
                        <li>Langkah 1</li>
                        <li>Langkah 2</li>
                    </ul>
                </nav>
            </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <main>
        <header>
            <h1>Checkout Reservasi</h1>
            <p>Selesaikan pesanan Anda sebelum kuota habis diambil orang lain.</p>
        </header>
        <nav>
            <ol>
                <li><a href="detail_makanan.html">&check; Detail Makanan</a></li>
                <li><strong>2. Pengisian Data</strong></li>
                <li>3. Pembayaran</li>
            </ol>
        </nav>
```

### Tahap 2: Ringkasan Pesanan & Pembayaran (Kiri)
**Prompt:**

> "Bagian selanjutnya dari halaman checkout adalah konten dua kolom. Kolom kiri kita representasikan menggunakan tag `<aside>`. Di dalam `<aside>` tersebut, pecah menjadi dua `<section>`: pertama untuk rincian biaya (gunakan struktur `<dl>`, `<dt>`, `<dd>` yang benar), dan section kedua untuk info ketersediaan metode pembayaran."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
            <div class="left-panel">
                <aside>
                    <div class="order-summary">
                        <section>
                            <h2>Ringkasan Pesanan</h2>
                            <div class="order-rows">...</div>
                        </section>
                    </div>
                </aside>
            </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <aside>
            <section>
                <h2>Ringkasan Pesanan Anda</h2>
                <p>Nasi Ayam Bakar Bumbu Rujak Spesial - Warung Bu Sari</p>
                <dl>
                    <dt>Jumlah Porsi</dt>
                    <dd>1 Porsi</dd>
                    <dt>Subtotal</dt>
                    <dd>Rp25.000</dd>
                    <dt>Diskon Surplus (52%)</dt>
                    <dd>-Rp13.000</dd>
                    <dt>Biaya Admin</dt>
                    <dd>Gratis</dd>
                </dl>
                <h3>Total Tagihan: Rp12.000</h3>
            </section>
            
            <section>
                <h2>Metode Pembayaran Tersedia</h2>
                <ul>
                    <li>QRIS (OVO, GoPay, ShopeePay, Dana, LinkAja)</li>
                    <li>Tunai di Tempat (Bayar saat ambil)</li>
                </ul>
            </section>
        </aside>
```

### Tahap 3: Form Data Pengambil (Kanan)
**Prompt:**

> "Untuk kolom kanannya, buat elemen `<section>`. Sediakan `<form action="payment_sukses.html">` panjang yang meminta data-data pengambil makanan. Bungkus kelompok input (seperti identitas, opsi wadah, dan estimasi jam ambil) dengan elemen `<fieldset>` dan gunakan `<legend>` yang sesuai, agar sangat patuh pada struktur form yang aksesibel. Akhiri form dengan tombol submit pembayaran."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
            <div class="right-panel">
                <section>
                    <div class="form-container">
                        <h2>Langkah 2 - Data Pengambil</h2>
                        <form>
                            <div class="input-group">...</div>
                        </form>
                    </div>
                </section>
            </div>
        </main>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <h2>Langkah 2 &middot; Data Pengambil Makanan</h2>
            <form action="payment_sukses.html" method="get">
                <fieldset>
                    <legend>Identitas Diri</legend>
                    <label for="namaLengkap">Nama Lengkap (Sesuai KTP/KTM)</label>
                    <input type="text" id="namaLengkap" name="namaLengkap" placeholder="Masukkan nama lengkap" required>
                    
                    <label for="noWhatsapp">Nomor WhatsApp Aktif</label>
                    <input type="tel" id="noWhatsapp" name="noWhatsapp" placeholder="08..." required>
                </fieldset>
                
                <fieldset>
                    <legend>Opsi Wadah Makanan</legend>
                    <label>
                        <input type="radio" name="wadah" value="bawa_sendiri" checked> 
                        Bawa Kotak Makan Sendiri (+50 Poin Green Rescue)
                    </label>
                    <label>
                        <input type="radio" name="wadah" value="disediakan"> 
                        Gunakan Kotak dari Warung (Tanpa tambahan biaya)
                    </label>
                </fieldset>

                <fieldset>
                    <legend>Estimasi Kedatangan</legend>
                    <label for="jamAmbil">Pilih Jam Ambil (Rentang 19.30 - 20.30):</label>
                    <select id="jamAmbil" name="jamAmbil" required>
                        <option value="19.30">19.30 WIB</option>
                        <option value="19.45">19.45 WIB</option>
                        <option value="20.00">20.00 WIB</option>
                        <option value="20.15">20.15 WIB</option>
                        <option value="20.30">20.30 WIB</option>
                    </select>
                </fieldset>
                
                <button type="submit">Lanjut ke Pembayaran QRIS &rarr;</button>
                <p><small>Dengan menekan tombol di atas, Anda menyetujui syarat dan ketentuan Food Rescue.</small></p>
            </form>
        </section>
    </main>
```

### Tahap 4: Halaman Pembayaran Sukses
**Prompt:**

> "Untuk Halaman Sukses Reservasi (payment_sukses.html), gunakan HTML5 semantik khusus komponen antarmuka, yakni elemen `<dialog>` dengan atribut `open` agar bertindak seperti modal yang mendominasi layar. Tampilkan tiket pengambilan (barcode reservasi), rincian lokasi ambil, serta navigasi balik menggunakan `<form method="dialog">` dengan tombol-tombolnya."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="success-page">
    <div class="dialog-wrapper">
        <div class="dialog-box">
            <!-- Konten tiket penuh div -->
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <dialog open>
        <header>
            <h1>🎉 Pembayaran Berhasil!</h1>
            <p>Reservasi makanan surplus Anda telah dikonfirmasi.</p>
        </header>
        
        <section>
            <h2>Tiket Pengambilan (Food Rescue Pass)</h2>
            <p><strong>KODE: RES-8924-AB</strong></p>
            <img src="../../../assets/images/qr-dummy.png" alt="QR Code Pengambilan">
            <p><small>Tunjukkan QR Code ini kepada pihak warung.</small></p>
            
            <dl>
                <dt>Makanan:</dt>
                <dd>Nasi Ayam Bakar Bumbu Rujak Spesial (1 Porsi)</dd>
                <dt>Lokasi:</dt>
                <dd>Warung Bu Sari, Jl. Ketintang Baru No. 12</dd>
                <dt>Jadwal Ambil:</dt>
                <dd>Hari ini, 19.30 - 20.30 WIB</dd>
            </dl>
        </section>
        
        <form method="dialog">
            <button type="submit" onclick="window.location.href='riwayat_aktif.html'">Lihat Status Pesanan</button>
            <button type="button" onclick="window.location.href='index.html'">Kembali ke Beranda</button>
        </form>
    </dialog>
```

---

## Halaman Ulasan & Profil

### Tahap 1: Profil Layout & Ringkasan (Kiri)
**Prompt:**

> "Sekarang buatkan kerangka Halaman Profil Mahasiswa (profil.html). Aturan wajib tetap sama: TANPA DIV, gunakan HTML5 semantik saja. Di dalam `<main>`, gunakan `<aside>` di sisi paling kiri untuk menjadi wadah ringkasan identitas profil. Sisipkan foto profil, elemen `<meter>` untuk progres level, kemudian dua block `<section>` untuk daftar list definisi `<dl>` (statistik poin & penyelamatan) dan ul/li untuk warung favorit."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="profile-page">
    <div class="main-content">
        <div class="left-sidebar">
            <aside>
                <div class="user-card">
                    <!-- div soup user info -->
                </div>
            </aside>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <main>
        <aside>
            <section>
                <img src="../../../assets/images/avatar.png" alt="Foto Profil Raka Pratama">
                <h1>Raka Pratama</h1>
                <p><small>S1 Teknik Informatika - 2023</small></p>
                <strong>Green Rescuer - Level 3</strong>
                
                <p>340 / 500 poin <small>(160 poin lagi ke Level 4)</small></p>
                <meter value="340" min="0" max="500"></meter>
            </section>
            
            <section>
                <h2>Statistik Penyelamatan Pangan</h2>
                <dl>
                    <dt>18</dt>
                    <dd><small>Porsi Diselamatkan</small></dd>
                    
                    <dt>Rp214.000</dt>
                    <dd><small>Total Uang Dihemat</small></dd>
                    
                    <dt>7,6 kg</dt>
                    <dd><small>Emisi CO2e Dicegah</small></dd>
                </dl>
            </section>
            
            <section>
                <h2>Warung Favorit (Sering Diselamatkan)</h2>
                <ul>
                    <li>Warung Bu Sari <small>(5x diselamatkan)</small></li>
                    <li>Soto Cak Har <small>(3x diselamatkan)</small></li>
                    <li>Kedai Malam Unesa <small>(2x diselamatkan)</small></li>
                </ul>
            </section>
        </aside>
```

### Tahap 2: Pengaturan Akun & Preferensi (Kanan)
**Prompt:**

> "Pada kolom sebelahnya, sediakan elemen `<section>` besar yang menampung beragam formulir. Siapkan `<form>` dengan beberapa `<fieldset>` terpisah untuk mengganti: Data Diri & Kontak (input text/tel/email), Pengaturan Preferensi Makanan (radio dan checkbox filter diet), Pengaturan Notifikasi Push (checkbox radius kampus). Jangan tambahkan wrapper div satupun. Di bagian bawah section, sisipkan tautan logout dan ganti password."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="right-content">
            <section>
                <div class="form-wrapper">
                    <!-- banyak div form input-group -->
                </div>
            </section>
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <h2>Data Diri &amp; Kontak</h2>
            <form action="profil.html" method="post">
                <fieldset>
                    <legend>Informasi Pribadi</legend>
                    <label for="nama">Nama Lengkap</label>
                    <input type="text" id="nama" name="nama" value="Raka Pratama">
                    
                    <label for="nim">NIM Mahasiswa</label>
                    <input type="text" id="nim" name="nim" value="23051204117" readonly>
                    
                    <label for="wa">Nomor WhatsApp Aktif</label>
                    <input type="tel" id="wa" name="wa" value="081234567890">
                    
                    <label for="email">Email Kampus Terverifikasi</label>
                    <input type="email" id="email" name="email" value="rka.mahasiswa@unesa.ac.id" readonly>
                </fieldset>
                
                <button type="submit">Simpan Perubahan Data</button>
            </form>
            
            <h2>Pengaturan Preferensi Makanan</h2>
            <form action="profil.html" method="post">
                <fieldset>
                    <legend>Lokasi Kampus Utama</legend>
                    <label><input type="radio" name="kampus" value="ketintang" checked> Kampus Ketintang</label>
                    <label><input type="radio" name="kampus" value="lidah"> Kampus Lidah Wetan</label>
                </fieldset>
                
                <fieldset>
                    <legend>Filter Kebutuhan Diet &amp; Alergi</legend>
                    <label><input type="checkbox" name="diet" value="halal" checked> Wajib Halal</label>
                    <label><input type="checkbox" name="diet" value="vegetarian"> Vegetarian / Plant-based</label>
                    <label><input type="checkbox" name="diet" value="tidak_pedas" checked> Tidak Pedas / Level 0</label>
                    <label><input type="checkbox" name="diet" value="tanpa_kacang"> Alergi Kacang</label>
                    <label><input type="checkbox" name="diet" value="tanpa_seafood"> Alergi Seafood</label>
                </fieldset>
                
                <button type="submit">Perbarui Preferensi</button>
            </form>
            
            <h2>Pengaturan Notifikasi Push</h2>
            <form action="profil.html" method="post">
                <fieldset>
                    <legend>Pilih jenis notifikasi yang ingin diterima</legend>
                    <label><input type="checkbox" name="notif" value="flash_surplus" checked> Info Flash Surplus (Radius 2km dari kos)</label>
                    <label><input type="checkbox" name="notif" value="pengingat_ambil" checked> Pengingat 30 Menit Sebelum Jam Ambil Tutup</label>
                    <label><input type="checkbox" name="notif" value="warung_favorit" checked> Saat Warung Favorit Membuka Sesi Surplus</label>
                    <label><input type="checkbox" name="notif" value="promo_kampus"> Promo Khusus Mahasiswa &amp; Event Kampus</label>
                </fieldset>
                <button type="submit">Simpan Preferensi Notifikasi</button>
            </form>
            
            <section>
                <h2>Keamanan Akun &amp; Sesi</h2>
                <p><small>Terakhir login: Hari ini, 18.00 WIB dari Surabaya (Perangkat Mobile)</small></p>
                <a href="ganti_password.html">Ubah Kata Sandi Saat Ini</a>
                <a href="login.html">Keluar / Logout dari Perangkat Ini</a>
            </section>
        </section>
    </main>
```

### Tahap 3: Halaman Pendukung (Ulasan, QR, Sukses)
**Prompt:**

> "Untuk melengkapi halaman terakhir, buatkan beberapa desain simpel untuk halaman detail_pesanan.html (dengan form Beri Ulasan interaktif), ulasan_sukses.html (feedback sukses ulasan), scan_qr_code.html (tunjukkan QR besar untuk warung), dan pickup_berhasil.html (verifikasi sukses dari sisi mahasiswa). Semuanya harus mematuhi layout blok semantik yang murni."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="support-pages-wrapper">
    <div class="inner-content">
        <!-- Konten halaman lainnya dengan div-soup -->
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
<!-- Contoh salah satu halaman pendukung: ulasan_sukses.html -->
    <main>
        <section>
            <h1>Terima Kasih Atas Ulasan Anda!</h1>
            <p>Feedback Anda membantu Warung Bu Sari terus meningkatkan kualitas pelayanannya, dan membantu sesama mahasiswa menemukan makanan berkualitas.</p>
            <strong>+10 Poin Green Rescue Ditambahkan!</strong>
            
            <p>Total poin Anda sekarang: 350 / 500 Poin (Menuju Level 4)</p>
            
            <nav>
                <ul>
                    <li><a href="katalog.html">Cari Makanan Surplus Lainnya</a></li>
                    <li><a href="riwayat_selesai.html">Kembali ke Riwayat Pesanan</a></li>
                </ul>
            </nav>
        </section>
    </main>
```

## Tahap Tambahan: Perbaikan Dead Code & Validasi W3C (Final)

**Konteks Perbaikan:**

- **Dead Code / Alur Navigasi:** Memperbaiki alur navigasi dari `Katalog` -> `Detail Makanan` -> `Checkout` -> `Pembayaran` (`payment_sukses.html`). Mengubah aksi form (`method="POST"` menjadi `method="GET"`) agar kompatibel dengan lingkungan file statis lokal, dan menghapus elemen bottom navigation "Checkout" (dead code) pada halaman Katalog agar fokus langsung ke Detail Makanan (pembelian instan / opsi 1).
- **Validasi W3C HTML5:** Memastikan seluruh file HTML mahasiswa lolos uji [Nu Html Checker](https://validator.w3.org/nu/).
  - Mengganti tag `<section>` dan `<article>` yang tidak memiliki *heading* (`<h2>`-`<h6>`) menjadi `<div>` untuk menghindari peringatan 'lacks heading'.
  - Memperbaiki hierarki level heading yang melompat (misal dari `<h1>` langsung ke `<h3>`).
  - Memperbaiki masalah elemen bersarang (*nesting*) yang dilarang.

### Penjelasan Teknis & Alasan Perbaikan (Deep Dive)

1. **Kenapa Dead Code Navigasi Dihapus & Mengubah POST ke GET?**
   - **Navigasi UX:** Pengguna menghendaki alur "Pembelian Instan" (Opsi 1) untuk mahasiswa rantau, yang mana dari Katalog harus masuk dulu ke **Detail Makanan** untuk melihat alamat, deskripsi, stok porsi, dan harga pasti. Area *aside* keranjang/checkout di bawah katalog menjadi mubazir (dead code) dan mengganggu *user journey*, sehingga dihapus total.
   - **Method GET vs POST:** Karena lingkungan prototipe ini berjalan menggunakan file statis murni (`.html` lokal) tanpa *backend server* (seperti PHP/Node.js), penggunaan form dengan `method="POST"` akan menyebabkan peramban menghasilkan *error* "405 Method Not Allowed" atau *File Not Found*. Menggantinya menjadi `method="GET"` memungkinkan navigasi mulus antar halaman statis, seolah-olah mengirim query parameter sederhana.

2. **Kenapa `<section>` dan `<article>` tanpa Heading Disalahkan oleh W3C?**
   - Di dalam spesifikasi HTML5 Semantik, elemen *sectioning* seperti `<section>` dan `<article>` akan secara otomatis mendefinisikan "simpul baru" dalam garis besar dokumen (Document Outline).
   - *Screen reader* (pembaca layar untuk disabilitas) dan mesin pencari (SEO) mengharapkan setiap "simpul baru" ini memiliki judul (`h2`-`h6`) agar strukturnya dapat dibaca.
   - Jika tujuannya hanya untuk membungkus (*wrapper*) atau membagi *layout* secara visual—namun tidak memiliki konteks judul spesifik—aturan baku W3C mewajibkan kita menggunakan tag generik non-semantik yaitu `<div>`.

### Contoh Perbaikan Kode (Mahasiswa)

**1. Penghapusan Dead Code (Bottom Aside Checkout di Katalog)**

*Sebelum:*
```html
    <main>
        ...
        <aside>
            <p><strong>Total: Rp 0</strong></p>
            <form action="checkout.html" method="post">
                <button type="submit" disabled>Lanjut ke Pembayaran</button>
            </form>
        </aside>
    </main>
```

*Sesudah (Dihapus karena navigasi diarahkan langsung via kartu katalog ke detail makanan):*
```html
    <main>
        <section>
            <h2>Menu Spesial Hari Ini</h2>
            <article>
                <a href="detail_makanan.html">
                    <img src="../../../assets/images/nasi-ayam-bakar.png" alt="Nasi Ayam Bakar">
                    ...
                </a>
            </article>
        </section>
        <!-- Bottom aside telah dihapus -->
    </main>
```

**2. Perbaikan Struktur Section/Article tanpa Heading**

*Sebelum:*
```html
        <section>
            <form action="pembayaran.html" method="get">
                <!-- Elemen form -->
            </form>
        </section>
```

*Sesudah (Diubah ke div untuk menghindari error lacks heading di W3C):*
```html
        <div>
            <form action="pembayaran.html" method="get">
                <!-- Elemen form -->
            </form>
        </div>
```
