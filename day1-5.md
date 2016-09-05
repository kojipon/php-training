# Laravel 5 IDE Helper Generator

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Download laravel-ide-helper

```
$ composer require barryvdh/laravel-ide-helper --dev
$ composer require doctrine/dbal --dev
```

Add service provider to config/app.php

```
// config/app.php

'providers' => [
    ...
    
    Barryvdh\LaravelIdeHelper\IdeHelperServiceProvider::class,
],
```

Automatic PHPDoc generation for Laravel Facades

```
$ php artisan ide-helper:generate
```

Automatic phpDocs for models

```
$ php artisan ide-helper:models

 Do you want to overwrite the existing model files? Choose no to write to _ide_helper_models.php instead? (Yes/No):  (yes/no) [no]:
 > no
```
