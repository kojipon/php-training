# [WIP] Generate the Laravel CRUD

Login Homestead

```
$ vagrant ssh
$ cd ~/Code/Laravel
```

Download crud-generator

```
$ composer require infyomlabs/laravel-generator "5.1.x-dev"
$ composer require laravelcollective/html "5.1.x-dev"
$ composer require infyomlabs/core-templates "5.1.x-dev"
$ composer require infyomlabs/swagger-generator "dev-master"
$ composer require jlapp/swaggervel "dev-master"
$ composer require doctrine/dbal "~2.3"
```

Add service provider to config/app.php

```
// config/app.php

'providers' => [
    ...
    
    Collective\Html\HtmlServiceProvider::class,
    Laracasts\Flash\FlashServiceProvider::class,
    Prettus\Repository\Providers\RepositoryServiceProvider::class,
    \InfyOm\Generator\InfyOmGeneratorServiceProvider::class,
    \InfyOm\CoreTemplates\CoreTemplatesServiceProvider::class,
],
```

Add aliases to config/app.php

```
'aliases' => [
    ...

    'Form'      => Collective\Html\FormFacade::class,
    'Html'      => Collective\Html\HtmlFacade::class,
    'Flash'     => Laracasts\Flash\Flash::class,
],
```

Publish vendor

```
$ php artisan vendor:publish
```

Publish generator stuff

```
$ php artisan infyom:publish
```

Generate CRUD

```
$ php artisan infyom:scaffold Post

 Field: (name db_type html_type options) []:
 > title string,50 text

 Enter validations:  []:
 > body string,500 textarea
 
 > exit
 
 Do you want to migrate database? [y|N] (yes/no) [no]:
  > yes
```
