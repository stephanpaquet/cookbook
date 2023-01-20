# PHP 8.1: Enums

@see https://stitcher.io/blog/php-enums

```php
enum Status
{
    case DRAFT;
    case PUBLISHED;
    case ARCHIVED;

    public function color(): string
    {
        return match($this)
        {
            Status::DRAFT => 'grey',
            Status::PUBLISHED => 'green',
            Status::ARCHIVED => 'red',
        };
    }
}

Status::ARCHIVED->color(); // "red"
```
