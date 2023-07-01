```php
Route::get('/notification', [NotificationController::class, 'list'])->name('notification.list');
Route::put('/notification/{notification}/swapAsRead', [NotificationController::class, 'swapAsRead'])->name('notification.swapAsRead');
Route::put('/notification/markAllAsRead', [NotificationController::class, 'markAllAsRead'])->name('notification.markAllAsRead');
Route::delete('/notification/{notification}/delete', [NotificationController::class, 'delete'])->name('notification.delete');
```

```php
Route::controller(NotificationController::class)->group(function () {
    Route::get('/notification', 'list')->name('notification.list');
    Route::put('/notification/{notification}/swapAsRead', 'swapAsRead')->name('notification.swapAsRead');
    Route::put('/notification/markAllAsRead', 'markAllAsRead')->name('notification.markAllAsRead');
    Route::delete('/notification/{notification}/delete', 'delete')->name('notification.delete');
});
```
