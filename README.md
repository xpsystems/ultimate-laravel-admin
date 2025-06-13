# Ultimate Laravel Admin

A fully dynamic, zero-boilerplate admin panel for Laravel. Auto-scans your models, builds CRUD interfaces (list, show, create/edit, delete), dashboards, sidebars and relation-aware forms—with UUID support out of the box.

## Features

*   Auto-discover all `app/Models` and expose them as admin resources
*   Dynamic list, show, create/edit, delete views—no per-model views to write
*   Dashboard with counts for each model
*   Sidebar navigation generated from your models
*   Uses `$fillable` to drive forms and tables
*   Relation-aware selects (belongsTo, hasMany, belongsToMany, etc.)
*   UUID primary keys via a simple trait
*   Bulma CSS for lightweight, responsive styling

## Prerequisites

*   PHP ≥ 8.1
*   Laravel ≥ 10.x
*   Composer

## Installation

```
git clone https://github.com/your-org/ultimate-laravel-admin.git .
composer install
```

## Setup

1.  Copy `.env.example` to `.env` and configure your database
2.  Run migrations:
    
    ```
    php artisan migrate
    ```
    
3.  Publish and configure if needed:
    
    ```
    php artisan vendor:publish --tag=admin-config
    ```
    
4.  Ensure `App\Providers\AdminServiceProvider` is registered in `config/app.php`
5.  Serve your app:
    
    ```
    php artisan serve
    ```
    

## Usage

Visit [/admin](http://localhost:8000/admin) to see the dashboard. Click any resource in the sidebar to manage its records.

## Configuration

All settings live in `config/admin.php`:

*   `models_namespace` – namespace to scan for models
*   `resources` – manual overrides or additions

## Customization

*   Publish and tweak Blade views in `resources/views/admin`
*   Adjust Bulma classes or swap for your own CSS framework
*   Extend `AdminResourceController` to add custom actions
*   Add new model-scanning rules in `AdminServiceProvider`

## Key Files & Structure

```
app/
  Traits/Uuid.php
  Models/           ← your Eloquent models (auto-scanned)
  Providers/
    AdminServiceProvider.php

config/
  admin.php        ← resource namespace & manual overrides

routes/
  admin.php        ← all admin routes

app/Http/Controllers/
  AdminResourceController.php

resources/views/admin/
  layout.blade.php
  dashboard.blade.php
  index.blade.php
  form.blade.php
  show.blade.php
```

## License

MIT © XPSYSTEMS.eu
