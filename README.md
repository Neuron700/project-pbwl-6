<div align="center">

# 🏗️ Sistem Akademik Project 6

**Project 6 · MVC Sederhana (tanpa framework)**

Framework **MVC buatan sendiri** untuk Sistem Akademik: router, controller dasar, dan model dasar ditulis dari nol.

![PHP](https://img.shields.io/badge/PHP-8.0%2B-777BB4?logo=php&logoColor=white) ![MVC](https://img.shields.io/badge/Arsitektur-MVC-blue) ![MySQL](https://img.shields.io/badge/MySQL-MariaDB-4479A1?logo=mysql&logoColor=white) ![Composer](https://img.shields.io/badge/Composer-PSR--4-885630?logo=composer&logoColor=white) ![License](https://img.shields.io/badge/License-MIT-green.svg) ![Status](https://img.shields.io/badge/status-selesai%20%26%20teruji-brightgreen)

</div>

## 📖 Deskripsi

`.htaccess` mengubah URL menjadi `index.php?page=...`. `App\Core\Bootstrap` memetakan URL ke `Controller@action`, controller memanggil model, lalu view dirender di dalam layout. Tidak ada framework semua lapisan terlihat jelas.

## 📸 Tampilan

<table>
 <tr>
 <td width="50%"><img src="docs/screenshots/01-dashboard.png" alt="Dashboard"><br><sub>Dashboard</sub></td>
 <td width="50%"><img src="docs/screenshots/02-mahasiswa.png" alt="Modul Mahasiswa"><br><sub>Modul Mahasiswa</sub></td>
 </tr>
 <tr>
 <td width="50%"><img src="docs/screenshots/03-dosen.png" alt="Modul Dosen"><br><sub>Modul Dosen</sub></td>
 <td width="50%"><img src="docs/screenshots/04-matakuliah.png" alt="Modul Matakuliah"><br><sub>Modul Matakuliah</sub></td>
 </tr>
</table>

## ✨ Fitur

- 🧭 Router sendiri via `.htaccess` + `Bootstrap.php`
- 🎮 Controller: Index, Dashboard, Mahasiswa, Dosen, Matakuliah
- 🧠 Model dasar dengan koneksi PDO
- 👁️ View per modul di `app/views/`
- 🎨 Layout guest & dashboard di `layouts/`
- 🛑 Halaman 404 khusus
- ⚙️ Autoload Composer PSR-4

## 🧱 Teknologi

| Lapisan | Teknologi |
| --- | --- |
| Arsitektur | MVC buatan sendiri |
| Routing | `mod_rewrite` → `?page=` |
| Bahasa | PHP 8.0+ |
| Database | MySQL (PDO) |
| Autoload | Composer PSR-4 |

## 🏗️ Arsitektur

```mermaid
flowchart TD
 A[Browser] -->|/mahasiswa| B[.htaccess]
 B --> C[index.php?page=mahasiswa]
 C --> D[App\Core\Bootstrap]
 D --> E[App\Controllers\Mahasiswa]
 E --> F[App\Models\Mahasiswa]
 F --> G[(pbwl_samples_6)]
 E --> H[app/views/mahasiswa/index.php]
 H --> I[layouts/dashboard.php]
 I --> A
```

## 🚀 Instalasi

1. Aktifkan `mod_rewrite` Apache.
2. Import `database.sql` ke `pbwl_samples_6`.
3. Buka **http://localhost/project6/**.

## 🗂️ Struktur

```
project6/
├── app/
│ ├── core/ # Bootstrap, Controller, Model, Error
│ ├── controllers/ # Index, Dashboard, Mahasiswa, Dosen, Matakuliah
│ ├── models/
│ └── views/ # per modul + error/404
├── inc/
├── layouts/
├── .htaccess
├── database.sql
├── index.php
└── README.md
```

## 🗄️ Database

Database **`pbwl_samples_6`** di MySQL/MariaDB port **3307** (user `root`, password kosong).

File `database.sql` sudah diimpor. Jika perlu import ulang:

```bash
mysql -h 127.0.0.1 -P 3307 -u root pbwl_samples_6 < database.sql
```

> Database lain di XAMPP (termasuk `dbakademik`) sengaja tidak disentuh.

## ✅ Verifikasi

- `/` → 200
- `/?page=mahasiswa` → 200
- `/?page=dosen` → 200
- `/?page=matakuliah` → 200

## 🔗 Tautan

- GitHub: https://github.com/Neuron700/project-pbwl-6
- Aplikasi: http://localhost/project6/

## 📄 Lisensi

MIT
