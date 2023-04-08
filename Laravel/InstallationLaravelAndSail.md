## Installation de Laravel

https://laravel.com/docs/9.x/installation

```shell
composer global require laravel/installer
laravel new example-app
cd example-app
```

### Installation de Sail

Choisir les options en indiquant les chiffres séparés par des virgules

```shell
php artisan sail:install
./vendor/bin/sail up -d
```

## Création d'une alias pour sail
dans le fichier ~/.zshrc

```shell
alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
```




## Compilation des assets
./vendor/bin/sail npm install

./vendor/bin/sail npm run dev


http://localhost/


## Installation pour Laravel 8
```shell
composer create-project laravel/laravel laravel-8 "8.*"
cd laravel-8
php artisan sail:install
sail up -d

sail artisan -V
>> Laravel Framework 8.83.27
```

## Installation pour Laravel 9
```shell
composer create-project laravel/laravel laravel-9 "9.*"
cd laravel-9
php artisan sail:install
sail up -d

sail artisan -V
>> Laravel Framework 9.52.4
```

## Intallation de Jetstream et Inertial
```shell
sail composer require laravel/jetstream
sail php artisan jetstream:install inertia --teams
sail npm install --save-dev vite laravel-vite-plugin
sail composer require "tightenco/ziggy"   

sail npm install && sail npm run dev
```

