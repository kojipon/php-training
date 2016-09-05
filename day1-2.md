# Generate a simple CRUD implementation

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Download crud-generator

```
$ composer require appzcoder/crud-generator --dev
$ composer require laravelcollective/html "5.1.*" --dev
```

Add service provider to config/app.php

```
// config/app.php

'providers' => [
    ...
    
    Appzcoder\CrudGenerator\CrudGeneratorServiceProvider::class,
    Collective\Html\HtmlServiceProvider::class,
],
```

Add aliases to config/app.php

```
'aliases' => [
    ...

    'Form'      => Collective\Html\FormFacade::class,
    'HTML'      => Collective\Html\HtmlFacade::class,
],
```

Run composer dump-autoload

```
$ composer dump-autoload
```

Publish config file and generator template files

```
$ php artisan vendor:publish --provider="Appzcoder\CrudGenerator\CrudGeneratorServiceProvider"
```

Generate CRUD

```
$ php artisan crud:generate Posts --fields="title#string; content#text; category#select#options=technology,tips,health"
```

Database migration

```
$ php artisan migrate
```

Check on Browser

http://homestead.app/posts/
