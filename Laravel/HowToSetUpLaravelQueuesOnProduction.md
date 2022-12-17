# How to Set up Laravel Queues on Production

## Inspirations

- [https://gblend.medium.com/setting-up-supervisor-and-cron-for-laravel-queue-in-production-163a89603355]([https://youtu.be/iH4Skwaw-KU](https://youtu.be/iH4Skwaw-KU))
- [https://youtu.be/iH4Skwaw-KU](https://youtu.be/iH4Skwaw-KU)
-

## Créer une migration pour la table de la base de données des emplois de la file d'attente

```bash
php artisan queue:table
php artisan migrate
```

```php
Schema::create('jobs', function (Blueprint $table) {
    $table->bigIncrements('id');
    $table->string('queue')->index();
    $table->longText('payload');
    $table->unsignedTinyInteger('attempts');
    $table->unsignedInteger('reserved_at')->nullable();
    $table->unsignedInteger('available_at');
    $table->unsignedInteger('created_at');
});
```

## Modifier le .env

```
QUEUE_CONNECTION=sync

// pour 

QUEUE_CONNECTION=database
```

```shell
php artisan make:job SendAnEmail
```

### Cron 

```shell
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1

```
