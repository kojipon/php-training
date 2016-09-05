# Setup the Laravel development environment

## Create ssh key

If the ssh key already exists, skip this

```
$ ssh-keygen
```

## Setup laravel/homestead

Add vagrant box

```
$ vagrant box add laravel/homestead
```

Clone laravel/homestead

```
$ cd ~
$ git clone https://github.com/laravel/homestead.git Homestead
```

Initialize homestead

```
$ cd homestead
$ sh init.sh
```

Change cpus to Homestead.yaml

```
$ vi ~/.homestead/Homestead.yaml

- cpus: 1
+ cpus: 2
```

Add nfs setting to Homestead.yaml

```
$ vi ~/.homestead/Homestead.yaml

folders:
    - map: ~/Code
      to: /home/vagrant/Code
+     type: nfs
```

Create vagrant synced directory

```
$ mkdir -p ~/Code
```

Add hosts to /etc/hosts

```
$ sudo vi /etc/hosts

192.168.10.10 homestead.app
```

# Install laravel

Startup Vagrant

```
$ cd ~/HomeStead
$ vagrant up
```

Login homestead

```
$ vagrant ssh
```

Change directory

```
$ cd ~/Code
```

Install laravel installer

```
$ composer global require "laravel/installer"
```

Install laravel 5.1

```
$ composer create-project laravel/laravel:5.1.* Laravel
```

Change directory

```
$ cd Laravel
```

Change permission

```
$ sudo chmod -R a+w storage/*
$ sudo chmod -R a+w bootstrap/cache
```

Change APP_KEY

```
$ php artisan key:generate
```

Check installation in Browser

http://homestead.app


