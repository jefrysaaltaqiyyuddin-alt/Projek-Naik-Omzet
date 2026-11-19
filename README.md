# NaikOmzet 🛒📈
### Smart Cashier Berbasis Digital untuk Meningkatkan Efisiensi Pengelolaan Penjualan UMKM
**Mitra: Toko Firman (Labuhan Ratu, Kedaton, Bandar Lampung)**

---

## 👥 Tim Pengembang (Kelas IF 23 Dx)
* **Faurel Ridho Permana** — NPM: 24312107
* **Jefry Altaqqiyuddin** — NPM: 24312109
* **Alfin Triwahyudi** — NPM: 24312135
* **M. Rizky Arya Seto** — NPM: 24312187
* **Ferdi Kurniawan** — NPM: 24312108

---

## 🛠️ Technology Stack
* **Backend**: Laravel 12 (PHP 8.3+)
* **Frontend**: Vue.js 3 (Composition API)
* **Bridge**: Inertia.js (Modern Monolith)
* **CSS Framework**: Tailwind CSS
* **Database**: SQLite / MySQL (Didukung penuh)
* **Build Tool**: Vite

---

## 🚀 Fitur Utama Sistem
1. **Dashboard Operasional**: Ringkasan Omzet Hari Ini, Omzet Bulanan, Transaksi Hari Ini, Grafik Tren 7 Hari Terakhir, Widget Stok Menipis, dan Top 5 Produk Terlaris.
2. **Smart Cashier (POS)**: Pemilihan produk sembako cepat, pencarian live, keranjang belanja interaktif, kalkulasi otomatis total & kembalian, shortcut nominal pecahan uang tunai, pembayaran QRIS, dan pencetakan struk nota penjualan.
3. **Pembaruan Stok Otomatis**: Stok barang terpotong secara atomik dan *real-time* di database saat transaksi diselesaikan.
4. **Pengelolaan Produk & Stok**: CRUD produk sembako, SKU/barcode, harga beli (HPP), harga jual, filter kategori, dan filter khusus "Hanya Stok Menipis" untuk memudahkan restock ke supplier.
5. **Riwayat Transaksi Penjualan**: Log transaksi terstruktur dengan invoice unik (`TRX-YYYYMMDD-XXXX`), filter tanggal, filter metode bayar, dan cetak ulang nota.
6. **Laporan Omzet**: Rekapitulasi omzet berkala, rincian omzet harian, distribusi per metode bayar, dan estimasi laba kotor usaha.

---

## 🔑 Akun Demo (Preset Tersedia di Halaman Login)
* **Pemilik Toko (Admin)**: `admin@naikomzet.com` | Password: `password`
* **Petugas Kasir (POS)**: `kasir@naikomzet.com` | Password: `password`

---

## 💻 Panduan Menjalankan Proyek
```powershell
# 1. Masuk ke direktori
cd "c:\laragon\www\Projek Naik Omzet"

# 2. Build asset frontend
npm.cmd run build

# 3. Jalankan server lokal
php artisan serve
```
Akses di browser: **http://127.0.0.1:8000**

---

## 🧪 Menjalankan Pengujian Otomatis
```powershell
php artisan test tests/Feature/NaikOmzetFeatureTest.php
```

---

## 📄 Dokumen Spesifikasi
* [PRD.md](file:///c:/laragon/www/Projek%20Naik%20Omzet/PRD.md): Product Requirements Document lengkap sesuai rancangan presentasi inisiasi proyek.
* [LAPORAN_TAHAP_1.md](file:///c:/laragon/www/Projek%20Naik%20Omzet/LAPORAN_TAHAP_1.md): Dokumentasi pelaksanaan Tahap 1, hasil implementasi, dan kendala teknis serta solusinya.
