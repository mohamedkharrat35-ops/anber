# Anber

Anber is a Laravel-based e-commerce platform for selling traditional Tunisian sweets and clothing products — baklawa, ka3k, war9a, ma9roudh, mlabes, and more.

🔗 **Live demo:** [anber-production.up.railway.app](http://anber-production.up.railway.app)

## Features

- Product catalog with categories (sweets, clothing, etc.)
- Admin panel to add, edit, and delete products
- Image upload for products
- Pricing per piece and per kg
- Order management
- Session-based authentication

## Tech Stack

- **Backend:** Laravel 13
- **Database:** MySQL
- **Frontend:** Blade templates, CSS
- **Deployment:** Railway (Nixpacks)
- **Local dev:** XAMPP

## Getting Started Locally

### Prerequisites

- PHP 8.3 or higher
- Composer
- MySQL (via XAMPP or standalone)
- Node.js & npm (if compiling frontend assets)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/anber.git
   cd anber
   ```

2. **Install PHP dependencies**
   ```bash
   composer install
   ```

3. **Copy the environment file and generate an app key**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

4. **Configure your database** in `.env`
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=anber
   DB_USERNAME=root
   DB_PASSWORD=
   ```

5. **Create the database**

   Open phpMyAdmin (`http://localhost/phpmyadmin`) and create a new database named `anber` with collation `utf8mb4_unicode_ci`.

6. **Run migrations**
   ```bash
   php artisan migrate
   ```

7. **Link storage** (required for product images to display)
   ```bash
   php artisan storage:link
   ```

8. **Serve the application**
   ```bash
   php artisan serve
   ```

   The app will be available at `http://localhost:8000` (or whichever port is shown in your terminal).

## Project Structure

- `app/Http/Controllers/Admin/ProductController.php` — Admin product CRUD logic
- `resources/views/admin/products/` — Admin product views
- `database/migrations/` — Database schema
- `storage/app/public/products/` — Uploaded product images

## Deployment

This project is deployed on [Railway](https://railway.app) using Nixpacks for automatic PHP builds. Pushing to the connected branch triggers an automatic redeploy.

## License

This project is for personal/educational use.
