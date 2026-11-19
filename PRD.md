# PRD NaikOmzet v0.2

Smart Cashier Berbasis Digital untuk Meningkatkan Efisiensi Pengelolaan Penjualan UMKM

| Informasi | Keterangan |
| --- | --- |
| Nama Aplikasi | NaikOmzet |
| Versi Dokumen | 0.2 (memperluas v0.1 dengan dashboard, grafik omzet, dan kasir interaktif) |
| Tanggal | 19 November 2026 |
| Tim Pengembang | Faurel Ridho Permana (24312107), Jefry Altaqqiyuddin (24312109), Alfin Triwahyudi (24312135), M. Rizky Arya Seto (24312187), Ferdi Kurniawan (24312108) |
| Kelas | IF 23 Dx |
| Mitra | Toko Firman, Labuhan Ratu, Kecamatan Kedaton, Kota Bandar Lampung |
| Teknologi | Laravel (backend), Vue.js (frontend), Inertia.js (penghubung) |
| Referensi Prototipe | Visualisasi PRD, Dashboard Interaktif NaikOmzet (contoh data ilustrasi) |

## 1. Latar Belakang dan Permasalahan

Toko Firman adalah usaha UMKM di bidang perdagangan sembako seperti beras, minyak goreng, gula, dan telur. Pencatatan penjualan saat ini belum terstruktur. Akibatnya, data sulit diperiksa kembali, stok tidak selalu sesuai barang yang terjual, dan rekap omzet membutuhkan waktu serta rentan kesalahan. Pemilik juga belum punya gambaran tren omzet harian, mingguan, bulanan, atau tahunan.

| No | Permasalahan | Solusi di NaikOmzet | Fitur |
| --- | --- | --- | --- |
| 1 | Data produk dan stok belum terorganisasi | Pengelolaan produk dan stok dalam satu tempat | F-01, F-02 |
| 2 | Pencatatan transaksi belum tersimpan dengan baik | Transaksi tersimpan lengkap dengan waktu dan pencatat | F-03 |
| 3 | Stok tidak otomatis mengikuti barang terjual | Stok berkurang otomatis setelah transaksi tersimpan | F-04 |
| 4 | Riwayat penjualan sulit ditelusuri | Riwayat transaksi dapat difilter dan dicari | F-05 |
| 5 | Rekap omzet membutuhkan waktu dan rentan salah | Laporan dan grafik omzet dihitung dari data transaksi | F-06, F-08 |
| 6 | Tren omzet belum terlihat | Grafik omzet mingguan, bulanan, dan tahunan | F-08 |

## 2. Tujuan dan Manfaat

### 2.1 Tujuan Proyek

1. Mengembangkan aplikasi kasir digital yang mendukung penjualan UMKM.
2. Mengelola produk dan stok dengan mudah, termasuk peringatan stok menipis.
3. Mendigitalisasi transaksi penjualan secara terstruktur.
4. Mengotomatisasi pengurangan stok setelah transaksi berhasil disimpan.
5. Menyajikan riwayat transaksi, rekap omzet, dan grafik tren omzet.

### 2.2 Manfaat

| Pihak | Manfaat |
| --- | --- |
| Toko Firman | Mengelola produk dan stok, menelusuri transaksi, dan melihat tren omzet |
| Pemilik | Memantau omzet harian, mingguan, bulanan, dan tahunan dari satu dashboard |
| Petugas kasir | Mencatat transaksi lebih cepat dengan validasi stok otomatis |
| Tim pengembang | Menerapkan analisis, perancangan, implementasi, dan pengujian perangkat lunak |

## 3. Target Pengguna dan Hak Akses

| Pengguna | Peran | Kebutuhan Utama |
| --- | --- | --- |
| Pemilik toko | Administrator | Mengelola produk dan stok, memantau dashboard dan grafik omzet |
| Petugas kasir | Operator | Mencatat transaksi penjualan dengan cepat dan akurat |
| Pengguna internal lain | Disesuaikan | Perlu divalidasi dengan mitra |

Karakteristik pengguna: sebagian besar tidak memiliki latar belakang teknis, sehingga antarmuka harus sederhana, menggunakan bahasa Indonesia, dan dapat dipakai dari ponsel maupun komputer.

### 3.1 Matriks Hak Akses per Menu

| Menu | Pemilik | Petugas Kasir |
| --- | --- | --- |
| Dashboard | Ya | Tidak |
| Kasir | Ya | Ya |
| Produk | Ya | Tidak |
| Stok | Ya | Tidak |
| Riwayat | Ya | Ya |
| Laporan dan Grafik Omzet | Ya | Tidak |

Hak akses petugas kasir masih perlu divalidasi dengan mitra.

## 4. Ruang Lingkup

**Termasuk dalam ruang lingkup:**

- Pengelolaan produk, stok, transaksi penjualan, riwayat, dan laporan omzet.
- Dashboard ringkasan dan grafik omzet mingguan, bulanan, dan tahunan.
- Autentikasi dengan dua peran: pemilik dan petugas kasir.
- Aplikasi web responsif yang dapat diakses dari ponsel dan komputer.

**Di luar ruang lingkup (tahap ini):**

- Pencetakan struk dan integrasi printer thermal.
- Pembayaran nontunai, dompet digital, atau QRIS.
- Pencatatan pelanggan dan program loyalitas.
- Pembukuan lengkap (laba rugi, pajak, dan piutang).
- Sinkronisasi multi-cabang.

## 5. Identifikasi Fitur Utama

| ID | Fitur | Deskripsi | Prioritas |
| --- | --- | --- | --- |
| F-01 | Pengelolaan Produk | Tambah, lihat, ubah, dan nonaktifkan data produk | Tinggi |
| F-02 | Pengelolaan Stok | Mencatat dan memantau jumlah persediaan setiap produk | Tinggi |
| F-03 | Transaksi Penjualan | Memilih produk, menentukan jumlah, dan menghitung total | Tinggi |
| F-04 | Pembaruan Stok Otomatis | Stok berkurang setelah transaksi berhasil disimpan | Tinggi |
| F-05 | Riwayat Transaksi | Melihat, mencari, dan memfilter transaksi tersimpan | Sedang |
| F-06 | Laporan Omzet | Rekap omzet dan jumlah transaksi berdasarkan rentang tanggal | Sedang |
| F-07 | Autentikasi Pengguna | Login dan pembatasan akses sesuai peran | Tinggi |
| F-08 | Dashboard dan Grafik Omzet | Ringkasan KPI, grafik omzet mingguan, bulanan, dan tahunan, produk terlaris, serta peringatan stok | Sedang |

## 6. User Flow

### 6.1 Alur Transaksi Penjualan (Petugas Kasir dan Pemilik)

1. Pengguna login ke aplikasi.
2. Pengguna membuka menu Kasir.
3. Pengguna memilih produk dari daftar produk aktif. Produk yang stoknya habis tidak dapat dipilih.
4. Pengguna menambah atau mengurangi jumlah barang di keranjang.
5. Sistem menghitung subtotal dan total pembayaran secara otomatis.
6. Pengguna menekan Simpan Transaksi.
7. Sistem memeriksa stok. Jika ada item yang melebihi stok, transaksi ditolak dan pesan peringatan ditampilkan.
8. Jika stok cukup, sistem menyimpan transaksi dan mengurangi stok dalam satu proses yang sama.
9. Sistem menampilkan konfirmasi. Transaksi baru muncul di riwayat dan dashboard ikut diperbarui.

### 6.2 Alur Pengelolaan Produk dan Stok (Pemilik)

1. Pemilik login dan membuka menu Produk.
2. Pemilik menambah produk baru (nama, harga, satuan, stok awal, batas stok menipis) atau mengubah data produk yang ada.
3. Pemilik menambah stok secara manual ketika ada barang masuk.
4. Pemilik menonaktifkan produk yang tidak lagi dijual. Produk yang pernah dipakai dalam transaksi tidak dihapus permanen.

### 6.3 Alur Dashboard, Riwayat, dan Laporan (Pemilik)

1. Pemilik membuka Dashboard dan melihat omzet hari ini, jumlah transaksi, rata-rata nilai transaksi, dan jumlah produk stok menipis.
2. Pemilik memilih periode grafik: Mingguan, Bulanan, atau Tahunan.
3. Sistem menampilkan grafik omzet dan jumlah transaksi beserta ringkasan periode.
4. Pemilik membuka Riwayat untuk melihat dan mencari transaksi.
5. Pemilik membuka Laporan dan memilih rentang tanggal untuk melihat total omzet dan jumlah transaksi.

## 7. Kebutuhan Fungsional

| ID | Kebutuhan | Deskripsi | Fitur |
| --- | --- | --- | --- |
| FR-01 | Login | Pengguna masuk menggunakan email dan kata sandi | F-07 |
| FR-02 | Pembatasan akses | Sistem membedakan akses pemilik dan petugas kasir sesuai matriks hak akses | F-07 |
| FR-03 | Tambah produk | Sistem menyimpan produk baru dengan nama (wajib), harga jual (angka positif), satuan, stok awal, dan batas stok menipis | F-01 |
| FR-04 | Lihat dan cari produk | Sistem menampilkan daftar produk beserta harga dan stok, dan dapat dicari berdasarkan nama | F-01, F-02 |
| FR-05 | Ubah dan nonaktifkan produk | Data produk dapat diubah. Produk yang pernah dipakai dalam transaksi dinonaktifkan, tidak dihapus permanen | F-01 |
| FR-06 | Pencatatan stok | Sistem menampilkan stok setiap produk dan mencatat penambahan stok secara manual | F-02 |
| FR-07 | Peringatan stok menipis | Produk yang stoknya sama dengan atau di bawah batas per produk ditandai sebagai menipis | F-02, F-08 |
| FR-08 | Pilih produk pada transaksi | Kasir memilih produk dari daftar produk aktif. Produk stok habis tidak dapat dipilih | F-03 |
| FR-09 | Input jumlah dan hitung total | Subtotal dihitung sebagai harga dikali jumlah, dan total seluruh item dihitung otomatis | F-03 |
| FR-10 | Validasi stok saat transaksi | Transaksi ditolak jika jumlah item melebihi stok, dengan pesan yang menyebut nama produk | F-03, F-04 |
| FR-11 | Simpan transaksi | Sistem menyimpan transaksi beserta item, tanggal dan waktu, serta pengguna pencatat | F-03 |
| FR-12 | Pengurangan stok otomatis | Setelah transaksi tervalidasi, sistem menyimpan transaksi dan mengurangi stok dalam satu proses. Keduanya berhasil atau gagal bersama | F-04 |
| FR-13 | Riwayat transaksi | Sistem menampilkan daftar transaksi terbaru di atas, dapat dicari berdasarkan ID atau nama produk, dan detailnya dapat dibuka | F-05 |
| FR-14 | Laporan omzet | Sistem menampilkan total omzet dan jumlah transaksi berdasarkan rentang tanggal yang dipilih | F-06 |
| FR-15 | Ringkasan dashboard | Dashboard menampilkan omzet hari ini, jumlah transaksi hari ini, rata-rata nilai transaksi, dan jumlah produk stok menipis | F-08 |
| FR-16 | Grafik omzet periode | Grafik menampilkan omzet (batang) dan jumlah transaksi (garis) untuk 12 minggu terakhir (Mingguan), 11 bulan tahun berjalan (Bulanan), dan 5 periode tahunan terakhir (Tahunan). Periode yang masih berjalan ditandai berbeda | F-08 |
| FR-17 | Ringkasan periode | Untuk periode yang dipilih, sistem menampilkan total omzet, rata-rata per periode, total transaksi, dan persentase pertumbuhan periode penuh terakhir dibanding periode sebelumnya | F-08 |
| FR-18 | Produk terlaris | Sistem menampilkan proporsi jumlah item terjual per produk dalam bentuk diagram donat | F-08 |
| FR-19 | Kasir interaktif | Kasir dapat menambah dan mengurangi jumlah item di keranjang, melihat sisa stok tersedia, dan melihat total secara langsung | F-03 |

## 8. Kebutuhan Nonfungsional

| ID | Kategori | Kebutuhan |
| --- | --- | --- |
| NFR-01 | Usability | Antarmuka menggunakan bahasa Indonesia, sederhana, dan dapat digunakan tanpa pelatihan panjang |
| NFR-02 | Responsivitas | Tampilan menyesuaikan layar ponsel dan komputer, termasuk grafik dan tabel |
| NFR-03 | Keandalan data | Transaksi dan pengurangan stok harus konsisten. Tidak boleh terjadi transaksi tersimpan tanpa pengurangan stok, atau sebaliknya |
| NFR-04 | Keamanan | Kata sandi disimpan dalam bentuk hash. Halaman dilindungi autentikasi dan perlindungan CSRF bawaan Laravel |
| NFR-05 | Kinerja | Menyimpan transaksi, memuat daftar produk, dan berpindah periode grafik harus terasa responsif. Target angka ditentukan saat pengujian |
| NFR-06 | Ketersediaan | Aplikasi dapat dijalankan di lingkungan lokal untuk pengembangan dan demonstrasi |
| NFR-07 | Pemeliharaan | Kode mengikuti struktur standar Laravel, Vue.js, dan Inertia.js, serta dikelola dengan Git |
| NFR-08 | Integritas data | Stok, harga, dan jumlah tidak boleh bernilai negatif |
| NFR-09 | Kompatibilitas | Berjalan pada browser modern (Chrome, Edge, Firefox, Safari) versi terbaru |
| NFR-10 | Aksesibilitas visual | Kontras teks memenuhi standar keterbacaan. Mendukung mode terang dan gelap mengikuti pengaturan perangkat |
| NFR-11 | Gerak | Animasi dinonaktifkan jika perangkat meminta pengurangan gerak (prefers-reduced-motion) |

## 9. Desain Antarmuka

### 9.1 Daftar Layar

| Layar | Isi Utama | Pengguna |
| --- | --- | --- |
| Login | Form email dan kata sandi | Semua |
| Dashboard | Kartu KPI, grafik omzet dengan tab Mingguan, Bulanan, dan Tahunan, ringkasan periode, produk terlaris, dan daftar stok | Pemilik |
| Kasir | Kartu produk dengan sisa stok, keranjang dengan kontrol jumlah, total, dan tombol Simpan Transaksi | Semua |
| Produk | Daftar produk dengan pencarian, tombol Tambah, Ubah, dan Nonaktifkan | Pemilik |
| Stok | Daftar stok per produk, tombol tambah stok, indikator menipis | Pemilik |
| Riwayat | Daftar transaksi terbaru dengan pencarian, halaman detail transaksi | Semua |
| Laporan | Pilihan rentang tanggal, total omzet, jumlah transaksi | Pemilik |

### 9.2 Komponen Utama

- **Kartu KPI:** empat kartu untuk omzet hari ini, transaksi hari ini, rata-rata nilai transaksi, dan produk stok menipis.
- **Grafik kombinasi:** batang untuk omzet dan garis untuk jumlah transaksi, dengan sumbu ganda. Batang periode berjalan ditampilkan lebih pudar.
- **Diagram donat:** proporsi produk terlaris.
- **Bilah stok:** setiap produk ditampilkan dengan bilah persentase. Produk menipis ditandai warna merah.
- **Stepper alur:** menampilkan langkah proses agar mudah diikuti pengguna baru.
- **Notifikasi singkat:** muncul di bagian bawah layar setelah transaksi tersimpan atau terjadi kesalahan.

### 9.3 Panduan Visual

- Warna utama indigo (#6366f1) dengan gradasi ke ungu (#8b5cf6).
- Warna keberhasilan hijau (#10b981), peringatan oranye (#f59e0b), dan kesalahan merah (#ef4444).
- Kartu dengan sudut membulat dan efek kaca halus. Font sans-serif modern dengan ukuran minimal 14 px untuk isi.
- Desain final tetap disepakati bersama mitra.

## 10. Rancangan Data (Perkiraan Awal)

| Entitas | Atribut Utama | Relasi |
| --- | --- | --- |
| users | id, nama, email, kata\_sandi (hash), peran | 1 user mencatat banyak transactions |
| products | id, nama, harga, satuan, stok, batas\_stok, aktif | 1 product muncul di banyak transaction\_items |
| transactions | id, user\_id, tanggal, total | 1 transaction memiliki banyak transaction\_items |
| transaction\_items | id, transaction\_id, product\_id, jumlah, harga, subtotal | Menghubungkan transactions dan products |

Catatan: struktur ini belum final dan akan disesuaikan saat implementasi. Harga pada transaction\_items disimpan sebagai salinan harga saat transaksi, agar riwayat tidak berubah ketika harga produk diubah.

## 11. Arsitektur Teknologi

| Komponen | Teknologi | Peran |
| --- | --- | --- |
| Backend | Laravel | Mengelola logika bisnis, basis data, autentikasi, dan rute |
| Frontend | Vue.js | Membangun komponen antarmuka yang interaktif |
| Penghubung | Inertia.js | Menghubungkan Laravel dan Vue.js tanpa API terpisah |
| Grafik | Chart.js | Menampilkan grafik omzet dan produk terlaris |
| Basis data | MySQL atau SQLite (pengembangan lokal) | Menyimpan data produk, stok, transaksi, dan pengguna |
| Versioning | Git dengan GitHub atau GitLab | Menyimpan source code dan riwayat pengembangan |

## 12. Kriteria Penerimaan

| ID | Skenario | Hasil yang Diharapkan |
| --- | --- | --- |
| KP-01 | Stok produk 8, kasir memasukkan jumlah 9 | Transaksi ditolak, pesan menyebut nama produk, stok tetap 8 |
| KP-02 | Transaksi berisi dua item valid | Transaksi tersimpan, stok kedua produk berkurang sesuai jumlah, total sesuai penjumlahan subtotal |
| KP-03 | Penyimpanan transaksi gagal di tengah proses | Tidak ada transaksi tersimpan dan tidak ada stok yang berkurang |
| KP-04 | Stok produk sama dengan batas menipis | Produk ditandai menipis dan muncul di ringkasan dashboard |
| KP-05 | Pemilik memilih grafik Mingguan | Grafik menampilkan 12 minggu terakhir dengan periode berjalan ditandai |
| KP-06 | Petugas kasir membuka URL Dashboard | Akses ditolak sesuai matriks hak akses |
| KP-07 | Produk pernah terjual lalu pemilik menghapusnya | Produk dinonaktifkan, tidak hilang dari riwayat transaksi |
| KP-08 | Pengguna ponsel membuka halaman Kasir | Tata letak satu kolom, tombol mudah ditekan, dan tidak ada elemen yang terpotong |

## 13. Rencana Iterasi

| Iterasi | Cakupan | Target |
| --- | --- | --- |
| 1 | F-01, F-02, F-03, F-04, F-07 | Transaksi, stok, dan login berjalan dengan validasi |
| 2 | F-05, F-06 | Riwayat, pencarian, dan laporan omzet |
| 3 | F-08 | Dashboard, grafik mingguan, bulanan, tahunan, dan produk terlaris |
| 4 | Pengujian dan validasi | Uji bersama mitra, penyesuaian, dan perbaikan |

## 14. Asumsi dan Hal yang Perlu Divalidasi dengan Mitra

1. Pengguna utama adalah pemilik toko dan petugas kasir. Peran tambahan belum ditentukan.
2. Aplikasi dibangun sebagai web responsif, bukan aplikasi native Android atau iOS.
3. Satuan dan kategori produk mengikuti daftar yang akan diberikan mitra.
4. Batas stok menipis ditentukan per produk oleh pemilik.
5. Transaksi belum memerlukan metode pembayaran dan perhitungan kembalian pada tahap ini.
6. Data awal produk akan diinput oleh tim atau pemilik toko.
7. Periode grafik (12 minggu, 11 bulan, 5 tahun) perlu dikonfirmasi sesuai kebutuhan pemilik.
8. Angka pada prototipe dashboard adalah contoh ilustrasi dan bukan data Toko Firman.

## 15. Panduan Penggunaan PRD untuk AI Coding Tools

- Dokumen ini menjadi konteks utama setiap instruksi yang diberikan kepada AI Coding Tools.
- Setiap prompt harus merujuk ke ID kebutuhan yang relevan, misalnya "Implementasikan FR-10 dan FR-12 sesuai PRD".
- Hasil yang dihasilkan AI wajib diperiksa terhadap PRD dan kriteria penerimaan sebelum di-commit.
- Setiap perubahan kebutuhan harus diperbarui di dokumen ini dan dicatat melalui commit.

## 16. Riwayat Perubahan

| Versi | Tanggal | Perubahan |
| --- | --- | --- |
| 0.1 | 19 November 2026 | Draft awal: latar belakang, fitur F-01 sampai F-07, FR-01 sampai FR-15, NFR-01 sampai NFR-09 |
| 0.2 | 19 November 2026 | Menambahkan F-08 dashboard dan grafik, FR-16 sampai FR-19, NFR-10 dan NFR-11, desain antarmuka, rancangan data, kriteria penerimaan, dan rencana iterasi |
