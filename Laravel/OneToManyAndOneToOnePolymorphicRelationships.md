One to Many & One to One Polymorphic Relationships | Laravel Eloquent Relationships

### TODO

- Commencer par les tests unitaires

### 5.1 One to Many & One to One Polymorphic Relationships | Laravel Eloquent Relationships

https://youtu.be/QAfTYrDhdHE

SynchronizationDetail

```php
protected $guarded = [];

public function configurations()
{
    return $this->morphMany(Configuration::class, 'configurable');
}
```

OtherModel

```php
protected $guarded = [];

public function configurations()
{
    return $this->morphMany(Configuration::class, 'configurable');
}
```

Configuration
configurable_id 1
configurable_type SynchronizationDetail
key
value

```php
protected $guarded = [];

public function configurable ()
{
    return $this->morphTo();
}
```

```php
$table->bigIncrements('configurable_id');
$table->string('configurable_type);
```

meme chose que

```php
$table->morphs('configurable);
```

```php
$synchronizationDetail = new SynchronizationDetail([
  # [...]
]);

$synchronizationDetail->configurations()->create([
  "key" => "token",
  "value" => "123456"
]);

$synchronizationDetail->configurations()->create([
  "key" => "other_config",
  "value" => "It's value"
]);
```

```php
$synchronizationDetail = SynchronizationDetail::find(1);

# On devrait avoir une collection de 2 model Configuration
dd($synchronizationDetail->configurations);
```

```php
$configuration = Configuration::find(1);

dd($configuration->configurable);

SynchronizationDetail::find(1)->synchronization->entity
```
