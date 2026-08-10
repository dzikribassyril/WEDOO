# WEDOO — Wedding Services Marketplace

A Laravel 11 wedding-services platform with a Filament 3 admin panel and Livewire customer pages, connecting couples with vendors across venues, catering, MCs, cars, makeup artists, photographers, and more.

![Laravel](https://img.shields.io/badge/Laravel-11-red)
![PHP](https://img.shields.io/badge/PHP-8.2-777bb4)
![Filament](https://img.shields.io/badge/Filament-3-orange)
![Livewire](https://img.shields.io/badge/Livewire-3-4e56a6)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-38bdf8)
![License](https://img.shields.io/badge/License-MIT-green)

## Features

- **Filament 3 admin panel** at `/admin` (auth-protected, collapsible sidebar, light theme) with CRUD resources for 14 entities: Venue, Gedung (building), Fasilitas (facilities), Akomodasi, Catering, Dokumentasi, Entertainment, MC, Mobil (car hire), Penghulu (wedding officiant), Perias (makeup artist), Souvenir, Vendor, and User
- Admin tables with search, sorting, money-formatted price columns, rich-text descriptions, and bulk delete actions
- **Customer-facing Livewire pages** listing vendors per category: venues, catering, documentation, entertainment, MCs, cars, makeup artists, souvenirs, and accommodation
- **Transaction tracking**: bookings recorded per customer (pelanggan) with vendor, total price, and transaction date
- **Auto-generated customer IDs** (e.g. `PLG-01`) with lock-safe sequential generation
- Bride (Istri) and Groom (Suami) pages, plus a contact page
- Authentication with register/login pages
- Spatie Laravel Media Library integration for file uploads

## Tech Stack

| Area | Technology |
|---|---|
| Framework | Laravel 11 |
| Language | PHP 8.2 |
| Admin panel | Filament 3 + Spatie Media Library plugin |
| Frontend | Livewire 3 + Volt, Blade, Tailwind CSS |
| Database | Eloquent ORM + migrations (13+ domain tables) |
| Testing | PHPUnit 11 |

## Project Structure

```
├── app/
│   ├── Filament/Resources/      # 14 admin CRUD resources
│   ├── Livewire/                # Customer pages + auth (Volt-enabled)
│   ├── Models/                  # Domain models (Venue, Catering, MC, ...)
│   └── Providers/               # App + Filament admin panel providers
├── database/migrations/         # users, venues, caterings, transaksis, ...
├── resources/views/livewire/    # Blade templates per category
├── routes/web.php               # Public routes
└── composer.json
```

## Installation

```bash
git clone https://github.com/dzikribassyril/WEDOO.git
cd WEDOO
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
```

## Usage

```bash
php artisan serve
```

Public pages (default `http://localhost:8000`):

| Route | Description |
|---|---|
| `/` | Vendor listings |
| `/venue`, `/catering`, `/mc`, `/mobil`, `/perias` | Category vendor pages |
| `/dokumentasi`, `/entertainment`, `/souvenir`, `/akomodasi` | Category vendor pages |
| `/transaksi`, `/detailtransaksi` | Transactions |
| `/istri`, `/suami` | Bride / groom pages |
| `/contact` | Contact page |
| `/login`, `/register` | Authentication |

Admin panel: `http://localhost:8000/admin`

## License

[MIT](LICENSE)
