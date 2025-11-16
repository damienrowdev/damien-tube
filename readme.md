# Damien Tube

A modern video platform built with Laravel and Vue.js, featuring user authentication, channels, and a beautiful Inertia.js-powered interface.

## Tech Stack

- **Backend**: Laravel 12 (PHP 8.2+)
- **Frontend**: Vue.js 3 with Inertia.js
- **Styling**: Tailwind CSS
- **Authentication**: Laravel Fortify
- **Database**: MySQL (via Docker)
- **Development**: Laravel Sail (Docker)

## Prerequisites

- Docker Desktop installed and running
- Git

## Getting Started

### 1. Install Dependencies

First, install PHP dependencies using Composer:

```bash
composer install
```

### 2. Set Up Environment

Copy the environment file and generate an application key:

```bash
cp .env.example .env
php artisan key:generate
```

### 3. Start Laravel Sail

Start the Docker containers:

```bash
./vendor/bin/sail up -d
```

This will start MySQL, Redis, and the Laravel application containers.

### 4. Run Migrations with Seeding

Run the database migrations and seed the database:

```bash
./vendor/bin/sail artisan migrate --seed
```

This will:
- Create all database tables (users, channels, etc.)
- Seed the database with a test user:
  - Email: `test@example.com`
  - Password: (check your seeder configuration)

### 5. Install Frontend Dependencies

Install Node.js dependencies:

```bash
./vendor/bin/sail npm install
```

### 6. Run the Development Server

Start the development server with hot module replacement:

```bash
./vendor/bin/sail npm run dev
```

The application will be available at:
- **Application**: http://localhost (or the port specified in your `.env` file)
- **Vite Dev Server**: http://localhost:5173

## Additional Sail Commands

- **Stop containers**: `./vendor/bin/sail down`
- **View logs**: `./vendor/bin/sail logs`
- **Run Artisan commands**: `./vendor/bin/sail artisan [command]`
- **Run Composer**: `./vendor/bin/sail composer [command]`
- **Run NPM**: `./vendor/bin/sail npm [command]`
- **Access MySQL**: `./vendor/bin/sail mysql`

## Project Structure

- `app/` - Laravel application code (Models, Controllers, etc.)
- `resources/js/` - Vue.js frontend code
- `routes/` - Application routes
- `database/migrations/` - Database migrations
- `database/seeders/` - Database seeders

## Features

- User authentication (registration, login, password reset)
- Settings management (profile, password, appearance)
- Modern, responsive UI with dark mode support

## Development

The application uses Vite for frontend asset compilation. When running `sail npm run dev`, Vite will watch for changes and automatically reload the browser.

For production builds:

```bash
./vendor/bin/sail npm run build
```

## License
MIT License
