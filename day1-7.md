# Xdebug in Eclipse

## Configure Xdebug

Login Homestead

```
$ vagrant ssh
```

Change xdebug.ini

```
$ sudo vi /etc/php/7.0/mods-available/xdebug.ini

xdebug.remote_enable = On
xdebug.remote_autostart = On
xdebug.remote_host = 192.168.10.1
```

Restart php-fpm

```
$ sudo service php7.0-fpm restart
```

Copy xdebug.ini for cli

```
$ sudo cp /etc/php/7.0/fpm/conf.d/20-xdebug.ini /etc/php/7.0/cli/conf.d/
```

## Configure Eclipse

Debug Configurations

```
Run > Debug Configurations… > PHP Web Application > Right click > New

Name: Homestead

Server tab >
    PHP Server: New
        Server tab > 
            Server Name: Homestead
            Base URL: http://homestead.app
        
        Debugger tab >
            Debugger: XDebug

        Path Mapping > Add
            Path on Server: /home/vagrant/Code/Laravel
            Path in Workspace: /Laravel
    
    File: /Laravel/public/index.php
    Auto Generate: OFF
    
Debugger tab >
    Break at First Line: ON
```


