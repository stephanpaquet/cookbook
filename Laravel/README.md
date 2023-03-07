# Cookbook Laravel

### Display all SQL executed in Eloquent

```php
use Illuminate\Support\Facades\Event;

Event::listen('illuminate.query', function($query) {
    var_dump($query);
});
```

