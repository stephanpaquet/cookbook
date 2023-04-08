# write me the code for a repository php pattern for laravel 9 please

Sure, here's an example of a repository pattern implementation in Laravel 9:

1.  First, create a new interface called UserRepository.php under app/Repositories:

```php
namespace App\Repositories;

interface UserRepository {
    public function getAllUsers();
    public function getUserById($id);
    public function createUser(array $attributes);
    public function updateUser($id, array $attributes);
    public function deleteUser($id);
}
```

2. Next, create a new class called EloquentUserRepository.php under app/Repositories:

```php
namespace App\Repositories;

use App\Models\User;

class EloquentUserRepository implements UserRepository {

    public function getAllUsers() {
        return User::all();
    }

    public function getUserById($id) {
        return User::find($id);
    }

    public function createUser(array $attributes) {
        return User::create($attributes);
    }

    public function updateUser($id, array $attributes) {
        return User::where('id', $id)->update($attributes);
    }

    public function deleteUser($id) {
        return User::destroy($id);
    }
}
```

3. Create a new service provider called RepositoryServiceProvider.php under app/Providers:

```php
namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use App\Repositories\UserRepository;
use App\Repositories\EloquentUserRepository;

class RepositoryServiceProvider extends ServiceProvider {

    public function register() {
        $this->app->bind(
            UserRepository::class,
            EloquentUserRepository::class
        );
    }
}
```

4. Finally, register the RepositoryServiceProvider in your config/app.php:

```php
'providers' => [
    // ...
    App\Providers\RepositoryServiceProvider::class,
],
```

You can now inject UserRepository into your controllers or other classes and use it to interact with the User model. For example:
```php
namespace App\Http\Controllers;

use App\Repositories\UserRepository;
use Illuminate\Http\Request;

class UserController extends Controller {

    protected $userRepository;

    public function __construct(UserRepository $userRepository) {
        $this->userRepository = $userRepository;
    }

    public function index() {
        $users = $this->userRepository->getAllUsers();
        return view('users.index', compact('users'));
    }

    public function store(Request $request) {
        $this->userRepository->createUser($request->all());
        return redirect()->route('users.index');
    }

    // ...
}

```
