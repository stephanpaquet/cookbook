Apologies for the oversight. Here's a cheat sheet for working with Laravel Events and Listeners:

1. Creating an Event:
```php
php artisan make:event EventName
```

2. Creating a Listener:
```php
php artisan make:listener ListenerName --event=EventName
```

3. Registering Listeners:
- Manually register the listeners in the `EventServiceProvider` class.
- In the `listen` property, map events to their corresponding listeners.

```php
protected $listen = [
    EventName::class => [
        Listener1::class,
        Listener2::class,
    ],
];
```

4. Dispatching an Event:
```php
event(new EventName($data));
```

5. Handling Events in Listeners:
- Listeners handle events by implementing the `Illuminate\Contracts\Queue\ShouldQueue` interface to run asynchronously (optional).

```php
class ListenerName
{
    public function handle(EventName $event)
    {
        // Handle the event
    }
}
```

6. Queued Listeners:
- Listeners can be queued by implementing the `ShouldQueue` interface.
- Listeners will be pushed to the queue and processed later.

```php
class ListenerName implements ShouldQueue
{
    public function handle(EventName $event)
    {
        // Handle the event (queued)
    }
}
```

7. Subscribing Multiple Listeners to an Event:
- Use the `EventSubscriber` interface to define a subscriber class.
- Map events to their listeners in the `subscribedEvents` method.

```php
use Illuminate\Contracts\Events\Dispatcher;

class EventSubscriber
{
    public function subscribe(Dispatcher $events)
    {
        $events->listen(
            EventName::class,
            Listener1::class
        );

        $events->listen(
            EventName::class,
            Listener2::class
        );
    }
}
```

8. Event Firing Conditionally:
- Use the `Illuminate\Support\Facades\Event` facade to conditionally fire events.

```php
use Illuminate\Support\Facades\Event;

Event::when(condition, function () {
    event(new EventName($data));
});
```

9. Event Naming Conventions:
- Laravel follows a naming convention for events and listeners.
- Events: `SomeAction` event.
- Listeners: `SomeAction` should be handled by `SomeActionListener`.

10. Manually Registering Events and Listeners:
- Use the `event` helper function to register listeners manually.

```php
event(EventName::class, [Listener1::class, Listener2::class]);
```

11. Event Discovery:
- Laravel's event discovery automatically registers events and listeners in Laravel 5.8 and above.
- Listeners should be within the `Listeners` namespace.
- Events should be within the `Events` namespace.

12. Event Wildcards:
- Use wildcards to register listeners for multiple events.

```php
protected $listen = [
    'event.*' => [
        Listener::class,
    ],
];
```

This cheat sheet covers the fundamental concepts and usage of Laravel Events and Listeners. However, there are more advanced features available, such as event subscribers, event priorities, event middleware, and event testing. Laravel's documentation provides comprehensive details on all the features of events and listeners: [Laravel Events and Listeners Documentation](https://laravel.com/docs/events).
