# Thrift.io - Mobile

## Deskripsi Aplikasi
**Thrift.io** adalah sebuah aplikasi *mobile* berbasis Flutter yang mengusung tema *slow fashion* dan *conscious shopping*. Aplikasi ini berfokus pada ekosistem *thrifting* (pasar barang bekas layak pakai) untuk mengurangi limbah *fashion* dan mempromosikan gaya hidup berkelanjutan. Selain berfungsi sebagai *marketplace* barang *preloved*, aplikasi ini juga menjadi pusat komunitas bagi para pecinta mode melalui fitur pencarian acara, berita terbaru, forum diskusi, hingga alat pengonsep pakaian (*outfit builder*).

## Anggota Tim
- **Luthfi Ahmad Fadhlan / 2506617203** 
- **Maulana Farrel Arvindra / 2506552802** 
- **Muhammad Nabil Hariri / 2506602302**
- **Marclay Ardell Taufiqurrachman Harahap / 2506621024**
- **Razan Alif Azhima / 2506632942** 

## Arsitektur & Teknologi
Aplikasi *mobile* ini dikembangkan menggunakan tumpukan teknologi lintas platform (*cross-platform*) yang terhubung dengan *backend* web dari Proyek Tengah Semester (PTS):
- **Frontend / Mobile Framework:** Flutter (Dart) dengan penerapan Material Design 3 dan manajemen *state* menggunakan `Provider`.
- **Networking & Session Management:** `pbp_django_auth` dan `http` untuk komunikasi RESTful API dan persistensi *cookies* autentikasi pengguna.
- **Backend & Web Service:** Django & Django REST Framework (DRF) yang di-*deploy* pada **PWS (Pacil Web Service)** sebagai penyedia *endpoint* JSON.
- **Database:** SQLite / PostgreSQL (terpusat pada *backend* Django di PWS sehingga data tersinkronisasi antara versi web dan *mobile*).
- **Integrasi Pihak Ketiga (Flutter Packages & Public API):**
  - `flutter_map` / OpenStreetMap API untuk pemetaan lokasi acara *thrifting*.
  - `image_picker` & Poof.bg API untuk unggah foto dan penghapusan latar belakang (*background removal*) pada modul *Outfit Builder*.
  - NewsAPI / *endpoint* kurasi berita *fashion* untuk modul *Fashion News*.

## Fitur Utama & Daftar Modul Rencana

1. **Modul Autentikasi & Profil Pengguna (Marclay Ardell Taufiqurrachman Harahap)**
   - Registrasi, login, logout, dan manajemen profil pengguna yang terintegrasi dengan sesi Django.
2. **Modul Preloved Items Marketplace (Muhammad Nabil Hariri (Seller) & Luthfi Ahmad Fadhlan (Buyer))**
   - CRUD (*Create, Read, Update, Delete*) daftar barang *preloved*.
   - Pencarian, filter kategori, dan sistem transaksi/keranjang belanja.
3. **Modul Fashion/Thrifting Event Near You (Razan Alif Azhima)**
   - Pemetaan interaktif dan daftar acara *fashion* (bazaar, pameran, *swap meet*) di sekitar pengguna.
4. **Modul Fashion News (Marclay Ardell Taufiqurrachman Harahap)**
   - Agregasi dan kurasi artikel atau berita terbaru seputar *slow fashion* dan tren mode.
5. **Modul Fashion Forum (Maulana Farrel Arvindra)**
   - Wadah diskusi komunitas untuk berbagi tips *styling*, perawatan baju, dan diskusi *sustainable fashion*.
6. **Modul Outfit Builder from Photos (Razan Alif Azhima)**
   - Fitur interaktif di mana pengguna dapat mengunggah foto pakaian dari galeri/kamera, menghapus latar belakangnya, dan memadupadankan (*mix and match*) pakaian di atas kanvas virtual.

## Peran Pengguna (User Roles)
Aplikasi ini mendukung beberapa tingkatan akses pengguna:
1. **Guest (Pengunjung Belum Login):** Dapat melihat artikel berita, daftar acara di peta, serta melihat-lihat katalog *marketplace* dan membaca forum diskusi publik.
2. **Registered User (Pembeli & Penjual):** Memiliki akses penuh untuk menjual barang *preloved*, membeli barang, berpartisipasi (membuat *thread*/komentar) di forum, menyimpan acara, dan menggunakan fitur *outfit builder*.
3. **Admin/Moderator:** Memiliki hak akses untuk mengelola pengguna, menyetujui/menghapus *listing* barang yang melanggar aturan, mengelola artikel berita, serta memoderasi forum.

## Alur Pengintegrasian Data (Flutter & PWS via Django)
...