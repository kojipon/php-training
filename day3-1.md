# Functional Test

Create Database for testing

```
$ mysql -uhomestead -p -e 'create database homestead_testing'
```

Add connection for testing to ~/Code/Laravel/config/database.php

```
~/Code/Laravel/config/database.php

'connections' => [

    'mysql' => [
        ...
    ],
    
    'testing' => [
        'driver' => 'mysql',
        'host' => env('DB_HOST', 'localhost'),
        'database' => env('DB_DATABASE', 'forge') . '_testing',
        'username' => env('DB_USERNAME', 'forge'),
        'password' => env('DB_PASSWORD', ''),
        'charset' => 'utf8',
        'collation' => 'utf8_unicode_ci',
        'prefix' => '',
        'strict' => false
    ],
```

Create migration table

```
$ php artisan migrate:install --database=testing
```

Migrate database

```
$ php artisan migrate --database=testing
```

Add DB_CONNECTION to phpunit.xml

```
~/Code/Laravel/phpunit.xml

<php>
    ...
    <env name="DB_CONNECTION" value="testing"/>
</php>

```