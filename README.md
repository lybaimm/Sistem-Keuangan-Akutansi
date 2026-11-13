<div align="center">

# 📘 bukuku.id

**Aplikasi Akuntansi & Pembukuan Berbasis Web yang Sederhana, Cepat, dan Akurat untuk UMKM serta Organisasi.**

[![Next.js](https://img.shields.io/badge/Next.js-App_Router-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Prisma](https://img.shields.io/badge/Prisma-ORM-2D3748?style=flat-square&logo=prisma)](https://www.prisma.io/)
[![Database](https://img.shields.io/badge/Database-SQLite_%7C_PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

[Fitur Utama](#-fitur-utama) • [Teknologi](#-teknologi-yang-digunakan) • [Struktur Proyek](#-struktur-proyek) • [Cara Instalasi](#-cara-instalasi--menjalankan) • [Kontribusi](#-kontribusi)

</div>

---

## 📖 Tentang Proyek

**bukuku.id** adalah platform akuntansi berbasis web yang dirancang untuk menyederhanakan pencatatan transaksi harian hingga penyusunan laporan keuangan standar. Aplikasi ini menjembatani kebutuhan pelaku usaha dan organisasi yang membutuhkan pembukuan rapi secara *real-time* tanpa harus memiliki latar belakang akuntansi yang mendalam.

Dengan alur kerja *end-to-end*, setiap transaksi yang dicatat melalui antarmuka kasir yang ramah pengguna akan otomatis terintegrasi ke dalam sistem akuntansi berpasangan (*double-entry*) dan langsung menghasilkan laporan keuangan yang akurat.

---

## ✨ Fitur Utama

* **🏢 Manajemen Multi-Organisasi & Multi-User**
  * Daftarkan satu atau lebih entitas bisnis/organisasi dalam satu platform.
  * Kelola hak akses anggota tim (pemilik usaha, admin keuangan, maupun staf kasir).
* **📊 Dashboard Eksekutif Real-Time**
  * Pantau kesehatan arus kas, total pemasukan, total pengeluaran, serta ringkasan aktivitas transaksi terkini dalam satu layar.
* **🗂️ Chart of Accounts (COA) Fleksibel**
  * Dilengkapi *template* bagan akun standar (Aset, Kewajiban, Ekuitas, Pendapatan, dan Beban) otomatis saat organisasi dibuat.
  * Mendukung penambahan dan penyesuaian kode akun sesuai kebutuhan spesifik bisnis.
* **🧾 Pencatatan Transaksi & Kasir Sederhana**
  * Antarmuka input transaksi yang intuitif sehingga staf non-akuntan dapat mencatat pemasukan dan pengeluaran harian tanpa khawatir salah menjurnal debit-kredit secara manual.
* **📑 Laporan Keuangan Otomatis**
  * Akumulasi data transaksi secara instan menjadi laporan keuangan siap pakai untuk meminimalkan *human error* dan menghemat waktu rekapitulasi.
* **🔐 Keamanan Autentikasi**
  * Sistem registrasi dan login yang diamankan menggunakan **JSON Web Token (JWT)** dan proteksi rute berbasis *middleware*.

---

## 🛠️ Teknologi yang Digunakan

| Kategori | Teknologi |
| :--- | :--- |
| **Framework Utama** | [Next.js](https://nextjs.org/) (App Router) |
| **Bahasa Pemrograman** | TypeScript / JavaScript |
| **ORM & Database** | [Prisma ORM](https://www.prisma.io/) (SQLite untuk *development*, siap migrasi ke PostgreSQL) |
| **Autentikasi & Keamanan** | JWT (`jose` / `jsonwebtoken`) & Next.js Middleware |
| **Styling & UI** | Tailwind CSS |

---

## 📂 Struktur Proyek

```text
bukuku.id/
├── prisma/
│   ├── schema.prisma            # Skema model database Prisma
│   ├── seed.ts                  # Data awal (seeding) untuk demo/pengujian
│   └── schema.postgresql.sql    # Skema SQL untuk deployment PostgreSQL
├── src/
│   ├── app/
│   │   ├── api/                 # Endpoint REST API (Auth, COA, Kasir, Laporan, Organisasi)
│   │   ├── dashboard/           # Halaman utama aplikasi (Dashboard, COA, Kasir, Laporan)
│   │   ├── login/               # Halaman masuk pengguna
│   │   ├── register/            # Halaman pendaftaran akun & organisasi
│   │   └── page.tsx             # Landing page publik
│   ├── lib/
│   │   ├── coa-templates.ts     # Template standar Chart of Accounts
│   │   ├── jwt.ts               # Utilitas pembuatan & verifikasi token JWT
│   │   └── prisma.ts            # Konfigurasi instance Prisma Client
│   └── middleware.ts            # Proteksi rute & validasi sesi pengguna
├── .env.example                 # Contoh konfigurasi environment variables
├── package.json
└── README.md
```

---

## 🚀 Cara Instalasi & Menjalankan

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di lingkungan lokal Anda:

### 1. Prasyarat
Pastikan Anda sudah menginstal:
* [Node.js](https://nodejs.org/) (versi 18.x atau lebih baru)
* `npm`, `yarn`, `pnpm`, atau `bun`

### 2. Clone Repositori
```bash
git clone https://github.com/username-anda/bukuku.id.git
cd bukuku.id
```

### 3. Instal Dependensi
```bash
npm install
```

### 4. Konfigurasi Environment Variables
Salin file `.env.example` menjadi `.env`, lalu sesuaikan nilainya:
```bash
cp .env.example .env
```
Contoh isi file `.env`:
```env
DATABASE_URL="file:./dev.db"
JWT_SECRET="ganti-dengan-kunci-rahasia-yang-aman"
```

### 5. Setup Database & Seeding Data
Jalankan migrasi Prisma dan isi database dengan data contoh (*dummy data*):
```bash
npx prisma generate
npx prisma db push
npx prisma db seed
```

### 6. Jalankan Server Development
```bash
npm run dev
```
Buka browser dan akses **[http://localhost:3000](http://localhost:3000)**.

---

## 📸 Cuplikan Antarmuka (Screenshots)

> *Tip: Anda dapat menambahkan tangkapan layar aplikasi di bagian ini agar repositori terlihat semakin menarik.*

| Landing Page | Dashboard Keuangan |
| :---: | :---: |
| ![Landing Page](https://via.placeholder.com/450x250?text=Preview+Landing+Page) | ![Dashboard](https://via.placeholder.com/450x250?text=Preview+Dashboard) |

| Menu Kasir & Transaksi | Laporan Keuangan |
| :---: | :---: |
| ![Kasir](https://via.placeholder.com/450x250?text=Preview+Menu+Kasir) | ![Laporan](https://via.placeholder.com/450x250?text=Preview+Laporan) |

---

## 🤝 Kontribusi

Kontribusi selalu terbuka untuk membuat **bukuku.id** menjadi lebih baik!

1. *Fork* repositori ini.
2. Buat *branch* fitur baru (`git checkout -b fitur/FiturBaru`).
3. *Commit* perubahan Anda (`git commit -m 'Menambahkan FiturBaru'`).
4. *Push* ke *branch* tersebut (`git push origin fitur/FiturBaru`).
5. Buat **Pull Request**.

---

## 📄 Lisensi

Proyek ini didistribusikan di bawah lisensi **MIT**. Lihat file `LICENSE` untuk informasi lebih lanjut.

<div align="center">
  <sub>Dibuat dengan ❤️ untuk membantu digitalisasi pembukuan UMKM Indonesia.</sub>
</div>
