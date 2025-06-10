# FinMate 💰

FinMate adalah aplikasi pengelolaan keuangan pribadi berbasis web yang ditujukan untuk membantu generasi muda Indonesia mengatur keuangan mereka secara efektif dan terstruktur. Tidak hanya sebagai pencatat transaksi, FinMate hadir sebagai asisten finansial yang edukatif, interaktif, dan mudah digunakan. Fitur-fitur unggulan mencakup pencatatan transaksi otomatis & manual, budgeting cerdas berbasis AI, pelacakan tujuan tabungan, serta visualisasi laporan keuangan.

---

## 🌐 Gambaran Umum Proyek

FinMate dirancang sebagai Progressive Web App (PWA) dengan pengalaman layaknya aplikasi native. Proyek ini terdiri dari dua bagian utama:

- 🧠 Backend: RESTful API untuk autentikasi, transaksi, dan integrasi data.
- 🎨 Frontend: Antarmuka pengguna interaktif dan responsif untuk mengelola keuangan.

Teknologi AI digunakan untuk mengotomatiskan pengkategorian transaksi dan memberikan saran budgeting yang personal.

---

## 🧱 Struktur Proyek

```
capstone-project-CC25-CF295/
├── backend/        # Node.js + Express + Firebase (API Server)
├── frontend/       # HTML + CSS + JS (Web Client / PWA)
```

---

## 🚀 Backend

### 🔧 Teknologi

- Node.js & Express.js
- Firebase Firestore (NoSQL, Realtime)
- JSON Web Token (JWT) untuk otorisasi API

### 📚 Dokumentasi API

Base URL (Development): `http://localhost:4000` <br>
Base URL (Production): `https://capstone-project-cc25-cf295-production.up.railway.app`

#### 📝 Register
- `POST /api/auth/register`
- Body: `{ name, email, password }`
- Response: `{ message, userId }`

#### 🔑 Login
- `POST /api/auth/login`
- Body: `{ email, password }`
- Response: `{ message, token, user { id, name } }`

#### 🔐 Login Google
- `POST /api/auth/google`
- Body: `{ email }`
- Response: `{ message, token, user { id, name, email } }`

#### 👤 Get User Profile
- `GET /api/users/:id`
- Header: `Authorization: Bearer <token>`
- Response: `{ id, name, email, phone, address, isGoogleUser }`

#### ✏️ Update User Profile
- `PUT /api/users/:id`
- Header: `Authorization: Bearer <token>`
- Body: `{ name, email, phone, address }`
- Response: `{ message }`

#### 📊 Dashboard Summary
- `GET /api/transactions/summary`
- Header: `Authorization: Bearer <token>`
- Response: `{ message, data { availableBalance, totalIncome, totalExpense } }`

#### ➕ Add Transaction
- `POST /api/transactions`
- Header: `Authorization: Bearer <token>`
- Body: `{ amount, type, description, date }`
- Response: `{ message, transactionId }`

#### 📁 Get All Transactions
- `GET /api/transactions`
- Header: `Authorization: Bearer <token>`
- Response: `{ message, transactions { transactionId, userId, type, description, amount, date } }`

---

## 🎨 Frontend

### 🔧 Teknologi

- HTML, CSS, JavaScript
- Webpack / Vite (module bundler)
- Firebase SDK
- Responsive Design
- PWA (Web Manifest + Service Worker)

### 🧹 Fitur Utama

- Autentikasi Pengguna (Login/Register)
- Dashboard Keuangan Interaktif
- Form Tambah Transaksi (Pemasukan & Pengeluaran)
- Riwayat Transaksi & Laporan
- Manajemen Akun & Profil
- Notifikasi Pop-up (Modal)
- Tampilan Simpel & Elegan

---

## ⚙️ Cara Menjalankan Proyek Secara Lokal

### 1. Clone Repository

```bash
git clone https://github.com/ShotZ9/capstone-project-CC25-CF295.git
cd capstone-project-CC25-CF295
```

### 2. Setup Backend

```bash
cd backend
npm install
```

Buat file `.env` dan masukkan konfigurasi Firebase:

```
FIREBASE_API_KEY=...
FIREBASE_PROJECT_ID=...
FIREBASE_AUTH_DOMAIN=...
```

Lalu jalankan:

```bash
npm start
```

Server berjalan di: `http://localhost:4000`

### 3. Setup Frontend

```bash
cd ../frontend
npm install
```

Pastikan konfigurasi Firebase frontend sudah dimasukkan di file config. Lalu jalankan:

```bash
npm start
```

Aplikasi berjalan di: `http://localhost:3000`

---

## ☁️ Deployment

Frontend dapat di-deploy menggunakan:

- GitHub Pages
- Netlify
- Vercel

Backend dapat menggunakan:

- Vercel (Serverless API)
- Heroku
- Google Cloud Run

---

## 👨‍💻 Kontributor

Tim CC25-CF295:

- Yoel Amadeo Pratomo – Machine Learning
- Rosalia Indah Dwi Putriningsih – Machine Learning
- Ahmad Fuad Fauzi – Machine Learning
- Cici Yulita – Front-End & Back-End
- Rangga Dwi Aditya Saputra – Front-End & Back-End
- Melinda Eviyanti – Front-End & Back-End

---

## Video Demo
(Video Demo)[https://drive.google.com/drive/folders/1iiimUxSNQ6S12_t0ckD2w9ITQKtwXDlO]

---

## 📄 Lisensi

Proyek ini dikembangkan sebagai bagian dari Capstone Project Dicoding x Kampus Merdeka 2025. Hak cipta dilindungi oleh masing-masing kontributor.
