# 🧺 WishWash - Laundry Management System

WishWash adalah solusi manajemen laundry terintegrasi yang dirancang untuk mendigitalisasi operasional laundry. Sistem ini mencakup pelacakan status cucian secara real-time, manajemen pesanan, inventaris, dan laporan keuangan untuk memudahkan pemilik laundry dan pelanggan.

## 🚀 Tech Stack

Project ini menggunakan kombinasi teknologi modern untuk performa dan skalabilitas tinggi:

- **Backend:** Golang (GORM, PostgreSQL Driver)
- **Database:** PostgreSQL 18
- **Web (Admin/Owner):** Next.js (React)
- **Mobile (Customer/Kurir):** Flutter (Dart)

---

## 📂 Struktur Folder Project
```text
WISHWASH-APP/
├── assets/              # Aset gambar/icon global
├── backend/             # Source code API (Golang)
│   ├── cmd/             # Entry point aplikasi (main.go)
│   ├── config/          # Konfigurasi Database & Environment
│   ├── controller/      # Handler & Logika bisnis per fitur
│   ├── middleware/      # Keamanan (Auth, dll)
│   ├── model/           # Definisi tabel database (GORM Structs)
│   ├── repository/      # Fungsi query langsung ke database
│   ├── route/           # Pengaturan endpoint API
│   ├── go.mod           # Dependency Manager Go
│   └── go.sum           # Checksum security Go
├── mobile/              # Source code App Customer & Kurir (Flutter)
│   ├── android/         # Build file khusus Android
│   ├── ios/             # Build file khusus iOS
│   ├── lib/             # Kodingan utama antarmuka & logika Dart
│   ├── pubspec.yaml     # Dependency Manager Flutter
│   └── README.md        # Dokumentasi spesifik mobile
├── web/                 # Source code Dashboard Admin (Next.js)
│   ├── public/          # Aset statis publik web
│   ├── src/             # Kodingan utama antarmuka & logika React
│   ├── package.json     # Dependency Manager Node.js
│   ├── next.config.ts   # Konfigurasi framework Next.js
│   └── README.md        # Dokumentasi spesifik web
├── .env                 # Environment variables (PENTING: Jangan di-push!)
└── README.md            # Dokumentasi utama project ini
```

---

## 🛠️ Persyaratan Sistem (Wajib Install)

Sebelum memulai, pastikan perangkat Anda sudah terinstall:
1. **Golang:** [Download Go](https://golang.org/dl/) (versi 1.20+)
2. **PostgreSQL:** [Download Postgres](https://www.postgresql.org/download/)
3. **DBeaver:** [Download DBeaver](https://dbeaver.io/download/) (Rekomendasi GUI Database)
4. **Node.js:** Untuk menjalankan Web Next.js
5. **Flutter SDK:** Untuk menjalankan aplikasi Mobile

---

## 💾 Setup Database

1. Buka **DBeaver** dan buat koneksi baru ke PostgreSQL lokal.
2. Buat database baru dengan nama: `wishwash_db`.
3. **Penting (Port):** Secara default PostgreSQL menggunakan port `5432`. Jika port tersebut sudah terpakai oleh versi lama, gunakan port `5433`.

## ⚙️ Konfigurasi Environment (.env)

Karena file `.env` asli tidak disertakan dalam repository demi keamanan, **setiap anggota tim wajib membuat file .env secara manual** di root folder (`WishWash-App/`) agar koneksi database dapat berjalan.

1. Buat file baru dengan nama `.env` di folder utama project.
2. Salin dan tempel konfigurasi berikut ke dalam file tersebut:
```env
# Database Configuration
DB_HOST=localhost
DB_PORT=5433
DB_USER=postgres
DB_PASSWORD=12345678
DB_NAME=wishwash_db

# Backend API URL
NEXT_PUBLIC_API_URL=http://localhost:8080
```

---

## 🏁 Setup Awal

Gunakan perintah ini di terminal VS Code untuk mengambil project pertama kali:
```bash
# 1. Clone repository ke komputer Anda
git clone [https://github.com/PBL-Kelompok6-WishWash/WishWash-App.git](https://github.com/PBL-Kelompok6-WishWash/WishWash-App.git)

# 2. Masuk ke folder project
cd WishWash-App

# 3. Setup Backend
cd backend
go mod tidy

# 4. Jalankan server backend
go run cmd/main.go
```

---

## 🔄 Panduan Git & Kerja Tim (Workflow)

Ikuti aturan ini agar kode antar anggota tidak bentrok:

### 1. Sebelum Mulai Kerja (Wajib Pull)
Biasakan menarik update terbaru dari tim sebelum Anda mulai mengedit kode.
```bash
git pull origin main
```

### 2. Menyimpan & Mengirim Hasil Kerja (Push)
Setelah selesai menambah fitur atau memperbaiki bug:
```bash
# Cek file yang berubah
git status

# Tambahkan semua perubahan
git add .

# Beri pesan perubahan (Harus Jelas)
git commit -m "feat: [nama_fitur] menambah tabel user"

# Kirim ke GitHub
git push origin main
```

### 3. Cara Mengatasi Conflict
Jika saat `git pull` muncul error "Conflict", buka file yang bermasalah di VS Code, pilih bagian kode yang ingin dipertahankan, simpan file, lalu ulangi proses `add`, `commit`, dan `push`.

---

## 🛡️ Aturan Kontribusi
- **Dilarang** push file konfigurasi pribadi atau `.env` yang berisi password asli.
- **Wajib** menjalankan aplikasi secara lokal (`go run`) sebelum melakukan push untuk memastikan kode tidak error.
- Gunakan folder `cmd/main.go` sebagai titik masuk utama aplikasi backend.

---
*Dibuat oleh Tim PBL Kelompok 6 - Teknologi Rekayasa Komputer (POLINES)*
