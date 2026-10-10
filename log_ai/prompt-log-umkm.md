# Log Penggunaan AI - Portal Mitra UMKM

## Halaman Buat Listing Makanan (`buat_listing_makanan.html`)

### Tahap 1: Setup Layout Utama & Header

**Prompt:**
> "Bertindaklah sebagai Ahli HTML5 Semantik. Buatkan kerangka untuk halaman 'Buat Listing Surplus' berdasarkan desain. ATURAN KETAT: TANPA CSS, tanpa div-soup. Buat `<header>` navigasi UMKM yang memuat logo dan link Dashboard dll. Setelah `<header>`, buat elemen `<main>`. Di dalam `<main>`, persiapkan `<form action="kelola_makanan.html" method="get">` yang nantinya akan memuat seluruh kartu input."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="header-container">
    <header>
        <div class="logo">
            <img src="logo.png" alt="Logo">
        </div>
        <div class="nav-links">
            <ul>
                <li><a href="dashboard.html">Dashboard</a></li>
            </ul>
        </div>
    </header>
</div>
<div class="main-content">
    <main>
        <div class="form-container">
            <form action="kelola_makanan.html" method="get">
                <!-- isi form -->
            </form>
        </div>
    </main>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <header>
        <a href="dashboard.html">
            <img src="../../../assets/images/logo_umkm.png" alt="Logo PlusFood" width="40" height="40">
            <strong>PlusFood</strong>
            <small>Kantin</small>
        </a>
        <nav>
            <ul>
                <li><a href="dashboard.html">Dashboard</a></li>
                <li><a href="kelola_makanan.html"><strong>Kelola Surplus</strong></a></li>
            </ul>
        </nav>
        <p>
            <a href="notifikasi.html" title="Notifikasi">Notifikasi (2)</a> &bull; 
            <a href="profil.html"><strong>Mas Danu</strong> <small>Pemilik</small></a>
        </p>
    </header>

    <main>
        <header>
            <p><small>Kelola Surplus / Tambah</small></p>
            <h1>Buat Listing Surplus</h1>
        </header>
        <form action="kelola_makanan.html" method="get">
            <!-- isi form -->
        </form>
    </main>
```

### Tahap 2: Input Dasar (Informasi Menu & Kemasan)

**Prompt:**
> "Di dalam form tadi, buat dua elemen `<article>` untuk 'Informasi Menu' dan 'Catatan Kemasan'. Di setiap article, tambahkan `<fieldset>` beserta `<legend>`. Susun barisan `<input>`, `<select>`, dan `<textarea>` murni tanpa div. Setiap input wajib di-bind ke `<label>` menggunakan ID. Hapus semua bungkus `<div>` yang mengelompokkan label dan input."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="card-section">
    <h2>Informasi Menu</h2>
    <fieldset>
        <legend>Detail Makanan</legend>
        <div class="input-group">
            <label>Nama Makanan</label>
            <input type="text" name="nama">
        </div>
        <div class="input-group">
            <label>Kategori</label>
            <select name="kategori">...</select>
        </div>
    </fieldset>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
            <article>
                <h2>Informasi Menu</h2>
                <fieldset>
                    <legend>Detail Makanan</legend>
                    <p>
                        <label for="nama-makanan">Nama Makanan</label><br>
                        <input type="text" id="nama-makanan" name="nama_makanan" required>
                    </p>
                    <p>
                        <label for="kategori">Kategori</label><br>
                        <select id="kategori" name="kategori" required>
                            <option value="Camilan Kering" selected>Camilan Kering</option>
                        </select>
                    </p>
                </fieldset>
            </article>
```

### Tahap 3: Kalkulator Modal & Tombol Navigasi

**Prompt:**
> "Masih di dalam form, buat `<article>` baru untuk Kalkulator Penyelamatan Modal. Jangan gunakan div. Gunakan elemen semantik seperti `<progress>` untuk persentase modal yang tertutup. Kemudian di akhir `<form>`, tambahkan dua `<button type="submit">` (Simpan Draf & Tayangkan Listing). Pastikan atribut `formaction` dan `formmethod` di-set agar tombol-tombol tersebut menavigasi ke kelola_makanan.html."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="calculator-box">
    <div class="calc-row">
        <span>Modal terselamatkan: 100%</span>
        <div class="progress-bar-bg">
            <div class="progress-bar-fill" style="width: 100%;"></div>
        </div>
    </div>
</div>
<div class="action-buttons">
    <a href="kelola_makanan.html"><button>Simpan Draf</button></a>
    <a href="kelola_makanan.html"><button>Tayangkan</button></a>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
            <article>
                <h2>Kalkulator Penyelamatan Modal</h2>
                <section>
                    <p>
                        <label for="modal-per-porsi">Modal per porsi</label><br>
                        <input type="number" id="modal-per-porsi" name="modal_per_porsi" value="3500">
                    </p>
                    <ul>
                        <li>Total modal (8 porsi): <strong>Rp 28.000</strong></li>
                        <li>Modal terselamatkan: <strong>100%</strong></li>
                    </ul>
                    <p>
                        <progress value="100" max="100">100%</progress>
                    </p>
                </section>
            </article>

            <p>
                <button type="submit" formaction="kelola_makanan.html" formmethod="get" name="action" value="draft">Simpan Draf</button>
                <button type="submit" formaction="kelola_makanan.html" formmethod="get" name="action" value="publish">Tayangkan Listing</button>
            </p>
```

---

## Halaman Kelola Makanan (`kelola_makanan.html`)

### Tahap 1: Setup Header & Statistik

**Prompt:**
> "Buatkan halaman 'Kelola Surplus' murni semantik HTML5. Buat `<header>` standar, lalu di dalam `<main>`, buat `<section>` yang menampilkan metrik surplus (seperti jumlah porsi tersedia). Susun item statistik menggunakan `<ul>` dan `<li>`, jangan gunakan grid berbasis `<div>`."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="stats-container">
    <div class="stat-card">
        <h3>19 Porsi</h3>
        <p>Siap diselamatkan</p>
    </div>
    <div class="stat-card">
        <h3>Rp 44.500</h3>
        <p>Potensi Omzet</p>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <h2>Ringkasan Sesi Malam Ini</h2>
            <ul>
                <li>
                    <h3>19 Porsi</h3>
                    <p>siap diselamatkan</p>
                </li>
                <li>
                    <h3>Rp 44.500</h3>
                    <p>Estimasi potensi omzet</p>
                </li>
            </ul>
        </section>
```

### Tahap 2: Daftar Sesi Surplus Aktif

**Prompt:**
> "Di bawah statistik, tambahkan `<section>` Daftar Sesi Surplus Aktif. Gunakan tag `<ol>` untuk menampilkan daftar menu. Setiap `<li>` akan berisi `<img alt>`, judul `<h4>`, keterangan sisa porsi, dan tag `<progress>` semantik untuk visualisasi penjualan. Hapus semua `<div>` pada kode."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="surplus-list">
    <div class="surplus-item">
        <div class="img-box">
            <img src="kripik.png" alt="kripik">
        </div>
        <div class="details">
            <h4>Paket Camilan</h4>
            <div class="bar">
                <progress value="4" max="8"></progress>
            </div>
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <section>
            <h2>Sesi Surplus Aktif</h2>
            <ol>
                <li>
                    <img src="../../../assets/images/kripik.png" alt="Paket Camilan Mlempem-Proof" width="50" height="50">
                    <h4>Paket Camilan Mlempem-Proof</h4>
                    <p><time datetime="PT1H42M">1j 42m</time> tersisa</p>
                    <p>4/8 porsi terjual</p>
                    <progress value="4" max="8">50%</progress>
                </li>
                <!-- li menu lainnya -->
            </ol>
        </section>
```

---

## Halaman Scan QR Code (`scan_qr_code.html`)

### Tahap 1: Tampilan Dashboard Belakang

**Prompt:**
> "Halaman scan QR code akan berjalan sebagai modal di atas dashboard. Tolong strukturkan `<main>` yang meniru tampilan dashboard. Gunakan `<section>`, `<article>`, dan `<ul>` untuk grafik dan statistik tanpa div-soup."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="bg-dashboard">
    <div class="section-kpi">
        <div class="kpi-card">
            <p>Porsi Terselamatkan</p>
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
    <main>
        <section>
            <h2>Indikator Kinerja Utama</h2>
            <ul>
                <li>
                    <img src="../../../assets/images/icon-recycle.svg" alt="" width="24" height="24">
                    <h3>Porsi Terselamatkan Hari Ini</h3>
                    <p><strong>16</strong> porsi / 23 target</p>
                </li>
            </ul>
        </section>
        <!-- Konten Dashboard berlanjut... -->
```

### Tahap 2: Modal Verifikasi & Detail Pembeli

**Prompt:**
> "Tambahkan elemen HTML5 `<dialog open>` di akhir file sebagai modal utama 'QR Valid'. Di dalamnya, buat `<article>` yang menampilkan ikon centang, dan detail pembeli (gunakan tag list deskripsi `<dl>` untuk menyusun informasi: Pembeli, NIM, Pembayaran). Jangan gunakan div flex/grid."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="modal">
    <div class="modal-body">
        <h2>QR Valid</h2>
        <div class="buyer-info">
            <div class="info-row">
                <span class="label">Pembeli</span>
                <span class="value">Raka Pratama</span>
            </div>
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <dialog open aria-labelledby="modal-title-valid">
            <article>
                <header>
                    <img src="../../../assets/images/icon-check-success.svg" alt="" width="32" height="32">
                    <h2 id="modal-title-valid">QR Valid</h2>
                    <p><code>SB-4X29A</code></p>
                </header>

                <dl>
                    <dt>Pembeli</dt>
                    <dd><strong>Raka Pratama</strong></dd>

                    <dt>NIM</dt>
                    <dd><strong>23051204117</strong></dd>

                    <dt>Pembayaran</dt>
                    <dd><strong>QRIS &bull; Lunas</strong></dd>
                </dl>
```

### Tahap 3: Form Checklist Navigasi Serah Terima

**Prompt:**
> "Terakhir di modal tersebut, tambahkan form checklist serah terima pesanan menggunakan `<form>`, `<fieldset>`, `<legend>`, dan 2 `<button>`: Batal & Serahkan. Navigasikan tombol Batal ke dashboard.html melalui anchor tag `<a>`, lalu setting navigasi pada tombol Serahkan Pesanan menuju pickup_sukses.html langsung dari `formaction`. Dilarang tag `<a>` bungkus button."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <form>
            <div class="checkbox-group">
                <input type="checkbox"><label>Cocokkan nama</label>
            </div>
            <div class="btn-group">
                <a href="dashboard.html"><button>Batal</button></a>
                <a href="pickup_sukses.html"><button type="submit">Serahkan</button></a>
            </div>
        </form>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
                <form action="#" method="post">
                    <fieldset>
                        <legend>Checklist Serah Terima Pesanan</legend>
                        <p>
                            <input type="checkbox" id="check-nama" name="verify_nama" checked required>
                            <label for="check-nama">Cocokkan nama dengan pembeli</label>
                        </p>
                        <p>
                            <a href="dashboard.html"><button type="button">Batal</button></a>
                            <button type="submit" formaction="pickup_sukses.html" formmethod="get">Serahkan Pesanan</button>
                        </p>
                    </fieldset>
                </form>
            </article>
        </dialog>
```

---

## Halaman Pickup Sukses (`pickup_sukses.html`)

### Tahap 1: Modal Pickup Berhasil (Dialog)

**Prompt:**
> "Struktur halaman pickup sukses adalah sama dengan dashboard, namun modal `<dialog open>`-nya berisi notifikasi berhasil serah terima. Buat modal tersebut hanya dengan `<article>`, tanpa memakai ID atau class CSS kotor. Tampilkan jumlah uang diterima dan makanan diselamatkan dalam list `<dl>`."

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
<div class="modal open">
    <div class="modal-box text-center">
        <h2>Pickup Berhasil!</h2>
        <div class="info-diterima">
            Diterima <span>Rp 5.000</span>
        </div>
    </div>
</div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
        <dialog open aria-labelledby="modal-title-sukses">
            <article>
                <header>
                    <img src="../../../assets/images/icon-check-success.svg" alt="" width="64" height="64">
                    <h2 id="modal-title-sukses">Pickup Berhasil!</h2>
                    <p>Pesanan <strong>SB-4X29A</strong> &mdash; Paket Camilan Mlempem-Proof telah diserahkan.</p>
                </header>

                <section>
                    <dl>
                        <dt>Diterima</dt>
                        <dd><strong>Rp 5.000</strong></dd>
                    </dl>
                    <dl>
                        <dt>Makanan diselamatkan</dt>
                        <dd><strong>250 g</strong></dd>
                    </dl>
                </section>
```

### Tahap 2: Navigasi Kembali ke Dashboard

**Prompt:**
> "Bagaimana saya mengarahkan user kembali ke Dashboard secara semantik dan valid W3C dari dalam elemen modal dialog tanpa Javascript dan tanpa error validator (seperti error bungkus button dengan anchor tag)?"

**Kode Asli dari AI (Div-Soup / Belum Dibersihkan):**

```html
        <div class="button-kembali">
            <a href="dashboard.html" class="btn btn-primary">
                <button>Kembali ke Dashboard</button>
            </a>
        </div>
```

**Kode Bersih (Setelah Diperbaiki & Lulus W3C):**

```html
                <form action="dashboard.html" method="get">
                    <p>
                        <button type="submit">Kembali ke Dashboard</button>
                    </p>
                </form>
            </article>
        </dialog>
```

## Tahap Tambahan: Perbaikan Dead Code & Validasi W3C (Final)

**Konteks Perbaikan:**

- **Validasi W3C HTML5:** Memastikan seluruh file HTML UMKM lulus uji [Nu Html Checker](https://validator.w3.org/nu/).
  - **Sectioning Element:** Mengubah `<section>` dan `<article>` yang sekadar dipakai untuk membungkus konten tanpa *heading* menjadi `<div>`.
  - **Atribut Datetime:** Memperbaiki atribut `datetime` pada elemen `<time>` yang mengandung format rentang tanggal tidak valid (misal: `2026-10-01/2026-10-14`) menjadi dua elemen `<time>` terpisah.
  - **Nesting `<button>` & `<a>`:** Memperbaiki *error* `<button>` di dalam `<a>` dengan cara menggunakan `<button>` murni yang disisipi `onclick="window.location.href='...'"` agar semantik dan gaya UI tetap utuh namun terhindar dari error nesting.
  - **Placeholder Select Required:** Menambahkan `<option value="" disabled>` sebagai awalan (*placeholder*) kosong pada setiap elemen `<select>` yang diberi atribut `required`, agar memenuhi standar validasi kriteria W3C.

### Penjelasan Teknis & Alasan Perbaikan (Deep Dive)

1. **Aturan Larangan Interactive Content Nesting (`<button>` dalam `<a>`)**
   - Spesifikasi W3C melarang bersarangnya dua elemen interaktif (Interactive Content). Tag `<a>` adalah interaktif (membuka tautan), dan tag `<button>` juga interaktif (memicu aksi form/skrip).
   - Bila disatukan, *browser* dan *screen reader* akan bingung menentukan *event* utama apa yang harus dieksekusi saat elemen tersebut diklik.
   - **Solusi:** Kita mencopot tag `<a>` dan meletakkan fungsi navigasinya di dalam atribut *native* JS `<button onclick="window.location.href='...'">`. Ini menjaga tampilan murni sebuah tombol, sekaligus mematuhi spesifikasi HTML5 secara sah.

2. **Parsing Mesin pada Atribut `<time>`**
   - Tag `<time>` khusus dirancang agar waktu yang tertera bisa dipahami oleh mesin (*machine-readable*), misalnya algoritma Google, kalender, atau pengingat. 
   - Nilai pada atribut `datetime` *wajib* mengikuti format standar kalender ISO (contoh: `2026-10-14`). W3C akan membuang format *range* waktu (`2026-10-01/2026-10-14`) karena mesin tidak menganggapnya sebagai "satu titik waktu" (Single Timestamp).
   - **Solusi:** Dipecah menjadi dua buah tag `<time>` yang mengapit tanda hubung, sehingga mesin bisa menerjemahkannya sebagai waktu *start* dan waktu *end* secara eksplisit.

3. **Logika Validasi `<select required>` HTML5**
   - Peramban HTML5 memiliki fungsi validasi bawaan pada elemen *form*. Untuk tag *dropdown* `<select>`, jika diberi atribut `required` (wajib diisi), *browser* harus mengecek apakah pengguna "sudah memilih opsi valid" atau "belum memilih sama sekali".
   - Jika baris pertama langsung berupa opsi valid (misal `value="BRI"`), maka *browser* menganggap *form* itu otomatis *Valid* tanpa interaksi pengguna, sehingga atribut `required` menjadi lumpuh (*useless*).
   - **Solusi:** W3C mewajibkan elemen `<option>` paling pertama bertindak sebagai *placeholder* (punya `value=""` kosong) sehingga ketika form disubmit, peramban akan memblokir dan meminta *user* untuk memilih jika pilihan masih di *placeholder* tersebut.

### Contoh Perbaikan Kode (UMKM)

**1. Perbaikan Struktur Article/Section tanpa Heading**

*Sebelum:*
```html
        <section>
            <h2>Tips Operasional</h2>
            <article>
                <p><strong>Tips Kasir:</strong> Diskon 50% di atas pukul 19.30 WIB...</p>
            </article>
        </section>
```

*Sesudah (Article diganti Div agar valid di W3C):*
```html
        <section>
            <h2>Tips Operasional</h2>
            <div>
                <p><strong>Tips Kasir:</strong> Diskon 50% di atas pukul 19.30 WIB...</p>
            </div>
        </section>
```

**2. Perbaikan Rentang Waktu (Atribut Datetime)**

*Sebelum:*
```html
        <p>
            <time datetime="2026-10-01/2026-10-14">1&ndash;14 Okt 2026</time>
        </p>
```

*Sesudah (Dipecah agar valid):*
```html
        <p>
            <time datetime="2026-10-01">1</time>&ndash;<time datetime="2026-10-14">14 Okt 2026</time>
        </p>
```

**3. Perbaikan Elemen Button di dalam Anchor**

*Sebelum:*
```html
        <p>
            <a href="scan_qr_code.html"><button type="button">Batal</button></a>
        </p>
```

*Sesudah (Menggunakan atribut onclick pada button):*
```html
        <p>
            <button type="button" onclick="window.location.href='scan_qr_code.html'">Batal</button>
        </p>
```

**4. Perbaikan Required Select Placeholder**

*Sebelum:*
```html
        <select id="pilihan-bank" name="bank" required>
            <option value="BRI" selected>BRI</option>
            <option value="BCA">BCA</option>
        </select>
```

*Sesudah (Menambahkan option kosong di awal):*
```html
        <select id="pilihan-bank" name="bank" required>
            <option value="" disabled>-- Pilih Bank --</option>
            <option value="BRI" selected>BRI</option>
            <option value="BCA">BCA</option>
        </select>
```
