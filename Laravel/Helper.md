# Création d'une helper

## Ajout de l'alias dans la configuration de l'application

### config/app.php

Ajout de la ligne **'Helper' => App\Helpers\Helper::class,** dans les aliases

```php 
'aliases' => Facade::defaultAliases()->merge([
    'Helper' => App\Helpers\Helper::class,
])->toArray(),
```

### app/Helpers/Helper.php

```php
<?php

namespace App\Helpers;

class Helper
{
    public static function shout(string $string)
    {
        return strtoupper($string);
    }
}
```

## Example d'utilisation

```php
use App\Helpers\Helper;

var_dump(Helper::shout("Un tests"));

// Résultat
string(8) "UN TESTS"

```
