<div align="center">

# ⚙️ DevOps Laravel

### Laravel application foundation for local development and delivery.

A Laravel 12 starter application with a Composer-based development workflow and frontend asset build.

![PHP](https://img.shields.io/badge/PHP-8.2%2B-777BB4?logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?logo=laravel&logoColor=white)
![Tests](https://img.shields.io/badge/Tests-PHPUnit-6C3?logo=php&logoColor=white)

</div>

---

## Tentang repository

Repository ini menyediakan fondasi aplikasi Laravel 12. Saat ini `composer.json` menunjukkan dependency inti Laravel, Tinker, PHPUnit, dan tool pengembangan Laravel. Tidak ada konfigurasi deployment atau pipeline CI/CD khusus yang diasumsikan oleh README ini.

## Teknologi

- PHP 8.2+
- Laravel 12
- Composer
- PHPUnit
- Node.js dan npm untuk aset frontend (bila dibutuhkan oleh aplikasi)

## Persyaratan

- PHP 8.2 atau lebih baru
- Composer
- Node.js dan npm untuk build aset
- Database yang kompatibel dengan konfigurasi Laravel

## Setup lokal

```bash
git clone https://github.com/ArdiannXyz/devops-laravel.git
cd devops-laravel

composer install
cp .env.example .env
php artisan key:generate
```

Atur koneksi database pada `.env`, kemudian jalankan migration. Jika frontend tersedia, pasang dependency dan build aset:

```bash
php artisan migrate
npm install
npm run build
php artisan serve
```

Untuk hot reload frontend, gunakan `npm run dev` di terminal terpisah. Aplikasi berjalan di [http://127.0.0.1:8000](http://127.0.0.1:8000).

## Development workflow

`composer dev` tersedia untuk menjalankan proses development bersamaan sesuai konfigurasi script Composer repository. Periksa `composer.json` untuk perintah aktual sebelum digunakan.

```bash
composer dev
```

## Testing

```bash
php artisan test
```

Perintah lainnya:

```bash
php artisan route:list       # Inspeksi route
php artisan schedule:list    # Inspeksi jadwal scheduler
php artisan optimize:clear   # Bersihkan cache Laravel
```

## Catatan deployment

README ini tidak mengklaim bahwa pipeline deployment, server, atau environment production telah dikonfigurasi. Untuk deployment, siapkan sendiri secrets, database, storage, queue/scheduler bila diperlukan, HTTPS, dan pengaturan production Laravel (`APP_ENV=production`, `APP_DEBUG=false`). Jangan commit `.env` atau credential.

---

<div align="center">

**A clean starting point for Laravel application development.**

</div>
