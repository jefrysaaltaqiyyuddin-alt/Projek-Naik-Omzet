# LAPORAN TUGAS PROYEK AKHIR – TAHAP 1
## INISIASI PROYEK DAN PERSIAPAN PENGEMBANGAN APLIKASI
### Sistem Smart Cashier NaikOmzet — Toko Firman

---

### Informasi Kelompok & Proyek

* **Nama Proyek**: **NaikOmzet**
* **Judul Lengkap**: *Smart Cashier Berbasis Digital untuk Meningkatkan Efisiensi Pengelolaan Penjualan UMKM*
* **Mata Kuliah**: Proyek Akhir (Tahap 1: Inisiasi dan Persiapan)
* **Kelas**: **IF 23 Dx**
* **Mitra Usaha**: **Toko Firman** (Sembako & Kebutuhan Sehari-hari, Labuhan Ratu, Kedaton, Bandar Lampung)
* **Anggota Tim Pengembang**:
  1. **Faurel Ridho Permana** — NPM: **24312107**
  2. **Jefry Altaqqiyuddin** — NPM: **24312109**
  3. **Alfin Triwahyudi** — NPM: **24312135**
  4. **M. Rizky Arya Seto** — NPM: **24312187**
  5. **Ferdi Kurniawan** — NPM: **24312108**

---

## 1. Penentuan & Penggunaan Technology Stack

Berdasarkan ketentuan tugas dan kebutuhan sistem kasir digital yang cepat dan interaktif, tim telah memilih dan mengonfigurasi *technology stack* berikut:

1. **Laravel (Backend Framework)**:
   - Berperan sebagai fondasi logika bisnis di sisi server, routing API internal, autentikasi pengguna, manajemen transaksi database (`DB::transaction`), dan *Object-Relational Mapping* (ORM) menggunakan Eloquent.
   - Menyediakan integritas data tingkat tinggi untuk mencegah kondisi *race condition* stok barang melalui *pessimistic locking* (`lockForUpdate`).

2. **Vue.js 3 (Frontend Framework)**:
   - Berperan sebagai pengelola antarmuka pengguna (*User Interface*) yang reaktif dan interaktif.
   - Digunakan dengan pendekatan *Composition API* (`<script setup>`) untuk mengelola keadaan keranjang belanja kasir (*cart*), pencarian instan (*live search*), perhitungan total, dan interaksi formulir secara instan tanpa perlu memuat ulang seluruh halaman (*no full-page reload*).

3. **Inertia.js (Penghubung Monolith Modern)**:
   - Berperan sebagai jembatan (*modern bridge*) yang menghubungkan Laravel dan Vue.js tanpa memerlukan pembuatan REST API terpisah yang rumit.
   - Menggabungkan kemudahan pengembangan monolitik Laravel dengan pengalaman pengguna aplikasi halaman tunggal (*Single Page Application* / SPA).

4. **Tailwind CSS & Vite (Styling & Build Tool)**:
   - Digunakan untuk styling tampilan yang modern, responsif, dan ramah pengguna dengan nuansa warna *Emerald & Slate* khas ritel modern.
   - Vite menyediakan *hot module replacement* (HMR) dan *production bundling* berkecepatan tinggi.

---

## 2. Ringkasan Dokumen Kebutuhan (PRD.md)

Dokumen **PRD.md** telah berhasil disusun secara menyeluruh di direktori utama proyek sebagai acuan tunggal pengerjaan aplikasi dan panduan *prompt* AI. Rangkuman poin kunci PRD meliputi:
- **Latar Belakang & Masalah**: Toko Firman menjual sembako yang perputarannya cepat, namun pencatatan masih rentan tidak teratur, pembaruan stok lambat, dan rekap omzet menyita waktu.
- **Tujuan Sistem**: Mengintegrasikan 4 pilar (Produk, Stok, Transaksi, Omzet) dalam satu aplikasi digital.
- **Target Pengguna**: Pemilik Toko (Admin) dan Petugas Kasir.
- **Ruang Lingkup 6 Fitur**:
  1. Pengelolaan Produk (Katalog sembako, SKU, harga modal/jual).
  2. Pengelolaan Stok (Pemantauan persediaan & peringatan stok menipis).
  3. Transaksi Penjualan (Smart Cashier POS, hitung otomatis, tunai/QRIS, cetak struk).
  4. Pembaruan Stok Otomatis (Pemotongan kuantitas stok seketika transaksi sukses).
  5. Riwayat Transaksi (Log penjualan terstruktur & penelusuran invoice).
  6. Laporan Omzet (Rekapitulasi pendapatan harian/bulanan & estimasi laba kotor).
- **Spesifikasi Kebutuhan**: 20 poin Kebutuhan Fungsional (FR-01 s.d. FR-20) dan Kebutuhan Non-Fungsional (keamanan, latensi < 200 ms, responsif mobile/tablet).

---

## 3. Hasil Implementasi Awal Aplikasi

Pada pertemuan Tahap 1 ini, tim tidak hanya menyiapkan struktur inisiasi, tetapi juga berhasil mengimplementasikan seluruh alur kerja inti (*core workflow*) dari aplikasi NaikOmzet:

### A. Struktur Database & Model
- **Tabel `categories`**: Mengelompokkan komoditas Toko Firman (Sembako Utama, Bumbu Dapur, Makanan Instan, Minuman & Kopi, Kebersihan).
- **Tabel `products`**: Menyimpan SKU, nama barang, satuan (`kg`, `liter`, `pouch`, `bks`, `karung`), harga modal (HPP), harga jual, kuantitas stok fisik, dan batas minimum stok.
- **Tabel `transactions`**: Menyimpan kode invoice unik (`TRX-YYYYMMDD-XXXX`), kasir bertugas, nama pelanggan, metode pembayaran (tunai/qris), total tagihan, nominal bayar, dan kembalian.
- **Tabel `transaction_items`**: Menyimpan rincian produk, kuantitas beli, harga satuan saat transaksi, dan subtotal harga.

### B. Fitur yang Telah Selesai Dikerjakan & Diuji
1. **Landing Page NaikOmzet (`/`)**:
   - Memperkenalkan sistem kasir digital dengan identitas Toko Firman dan profil kelompok mahasiswa pengembang IF 23 Dx.
   - Dilengkapi informasi akun demo untuk mempermudah penilaian.
2. **Dashboard Operasional (`/dashboard`)**:
   - Menampilkan 4 kartu ringkasan: Omzet Hari Ini, Transaksi Hari Ini, Katalog Produk, dan Peringatan Stok Menipis.
   - Grafik batang visual tren omzet 7 hari terakhir.
   - Widget peringatan stok kritis dan daftar 5 produk sembako paling laris.
3. **Smart Cashier / POS (`/pos`)**:
   - Katalog produk interaktif dengan filter kategori dan pencarian instan.
   - Keranjang kasir dinamis dengan tombol tambah/kurang kuantitas barang.
   - Kalkulasi otomatis total tagihan belanja dan nominal kembalian.
   - Tombol pintas pecahan nominal uang tunai (+10rb, +20rb, +50rb, +100rb, uang pas) serta opsi QRIS.
   - **Otomasi Pemotongan Stok**: Stok produk di database otomatis berkurang secara *real-time* begitu transaksi berhasil disimpan.
   - Modal struk nota penjualan digital yang siap dicetak ke printer kasir (`window.print()`).
4. **Pengelolaan Produk & Stok (`/products`)**:
   - Tabel katalog barang sembako dengan *badge* status stok (Aman, Menipis, Habis).
   - Fitur centang "Hanya Stok Menipis" untuk memudahkan pemilik menyusun daftar belanja restock.
   - Modal formulir tambah produk dan edit produk sembako.
5. **Riwayat Transaksi Penjualan (`/transactions`)**:
   - Log seluruh nota invoice dengan filter tanggal dan metode pembayaran.
   - Halaman detail struk (`/transactions/{id}`) yang dapat dicetak ulang.
6. **Laporan Omzet Penjualan (`/reports`)**:
   - Rekap omzet harian, estimasi Laba Kotor (Omzet dikurangi HPP modal barang), dan analisis metode pembayaran.
7. **Pengujian Otomatis (Automated Feature Tests)**:
   - Dibuat pengujian unit & fitur pada `tests/Feature/NaikOmzetFeatureTest.php`.
   - **Hasil: 7 tes lulus (100% Passed) dengan 13 assertions dalam waktu 296 ms.**

---

## 4. Kendala Teknis yang Ditemukan & Solusi Pemecahan

Selama inisiasi dan konfigurasi awal pada lingkungan pengembangan lokal Windows/Laragon, tim menemui beberapa kendala teknis berikut:

| No | Kendala yang Ditemukan | Penyebab | Solusi / Tindakan yang Dilakukan |
| :---: | :--- | :--- | :--- |
| 1 | `php` dan `composer` tidak terdeteksi langsung di command line standar PowerShell. | Variabel lingkungan `PATH` sistem belum menyertakan direktori binary Laragon (`C:\laragon\bin\php\...` dan `C:\laragon\bin\composer`). | Mengonfigurasi path PHP 8.3 dan Composer Laragon ke dalam sesi terminal sehingga perintah `php` dan `composer` berjalan lancar. |
| 2 | Composer lambat dan memunculkan peringatan *"The zip extension is missing, downloading from source"*. | Ekstensi `zip`, `pdo_sqlite`, dan `sqlite3` masih bertanda titik-koma (nonaktif) pada file `php.ini` bawaan Laragon. | Mengaktifkan baris `extension=zip`, `extension=pdo_sqlite`, dan `extension=sqlite3` pada `C:\laragon\bin\php\php-8.3.16-Win32-vs16-x64\php.ini`, sehingga Composer dapat mengunduh arsip paket secara cepat dan instan. |
| 3 | Pesan peringatan Execution Policy PowerShell pada eksekusi `npm.ps1`. | Kebijakan keamanan default PowerShell membatasi script eksekusi `.ps1`. | Menjalankan perintah Node package manager menggunakan `npm.cmd` (misal: `npm.cmd run build`), yang aman dan didukung penuh pada sistem operasi Windows. |
| 4 | Impor `./bootstrap` tidak ditemukan saat *first build* Vite setelah instalasi scaffolding Breeze. | File `resources/js/bootstrap.js` belum terbentuk secara otomatis pada instalasi minimal. | Membuat file `resources/js/bootstrap.js` dengan konfigurasi Axios standar dan header `X-Requested-With`, sehingga build Vite berhasil 100% tanpa kendala. |

---

## 5. Panduan Menjalankan Aplikasi di Lingkungan Lokal

Untuk menjalankan aplikasi NaikOmzet di komputer lokal:

### Langkah 1: Pengaturan Awal
Pastikan berada di direktori proyek:
```powershell
cd "c:\laragon\www\Projek Naik Omzet"
```

### Langkah 2: Build Asset Frontend
```powershell
npm.cmd run build
```
*(Atau gunakan `npm.cmd run dev` jika ingin menjalankan Vite development server secara langsung).*

### Langkah 3: Menjalankan Server Laravel
Jalankan server pengembangan:
```powershell
php artisan serve
```
Aplikasi akan aktif dan dapat diakses melalui browser pada URL:
**http://127.0.0.1:8000** atau **http://localhost:8000**

### Langkah 4: Kredensial Akun Pengujian (Demo Login)
Sistem telah dilengkapi dengan *Database Seeder* data Toko Firman:
* **Akun Pemilik Toko (Admin)**:
  - Email: `admin@naikomzet.com`
  - Password: `password`
* **Akun Petugas Kasir (POS)**:
  - Email: `kasir@naikomzet.com`
  - Password: `password`
*(Tersedia pula tombol 1-Click Login pada layar login untuk kemudahan demonstrasi).*

---

## 6. Rencana Kerja untuk Tahap Berikutnya (Tahap 2)

Setelah menyelesaikan inisiasi proyek, dokumen PRD, dan implementasi fitur utama pada Tahap 1, rencana pengembangan untuk Tahap 2 meliputi:
1. **Integrasi Barcode Scanner Hardware**: Pengujian pemindaian fisik barcode produk sembako langsung pada input kasir POS.
2. **Penyempurnaan Fitur Retur / Pembatalan Transaksi**: Mekanisme pembatalan nota transaksi yang otomatis mengembalikan jumlah stok barang (*stock rollback*).
3. **Ekspor Laporan Penjualan ke Excel & PDF**: Memungkinkan pemilik toko mengunduh laporan omzet bulanan ke file format `.xlsx` dan `.pdf` untuk keperluan arsip perpajakan atau laporan keuangan UMKM.
4. **Validasi & Uji Coba Pengguna Bersama Mitra**: Menguji coba antarmuka langsung bersama pemilik Toko Firman di lokasi Labuhan Ratu Bandar Lampung untuk mendapatkan umpan balik operasional.
