Certainly! Here's a cheat sheet for working with Laravel migrations:

1. Creating a Migration:
```php
php artisan make:migration create_table_name --create=table_name
```

2. Running Migrations:
```php
php artisan migrate
```

3. Rolling Back Migrations:
```php
php artisan migrate:rollback
```

4. Rolling Back All Migrations:
```php
php artisan migrate:reset
```

5. Rolling Back and Re-migrating:
```php
php artisan migrate:refresh
```

6. Creating a Table:
```php
Schema::create('table_name', function (Blueprint $table) {
    // Add columns to the table
    $table->id();
    $table->string('name');
    // ...
});
```

7. Modifying a Table:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Modify columns of the table
    $table->string('new_column')->nullable();
    // ...
});
```

8. Dropping a Table:
```php
Schema::dropIfExists('table_name');
```

9. Renaming a Table:
```php
Schema::rename('old_table_name', 'new_table_name');
```

10. Adding Columns to a Table:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Add new columns to the table
    $table->string('new_column')->nullable();
    // ...
});
```

11. Modifying Columns in a Table:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Modify existing columns in the table
    $table->string('column_name')->change();
    // ...
});
```

12. Dropping Columns from a Table:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Drop columns from the table
    $table->dropColumn('column_name');
    // ...
});
```

13. Foreign Key Constraints:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Add foreign key constraint
    $table->foreign('column_id')->references('id')->on('related_table')->onDelete('cascade');
});
```

14. Modifying Foreign Key Constraints:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Modify foreign key constraint
    $table->foreign('column_id')->references('id')->on('related_table')->onDelete('set null');
});
```

15. Indexes:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Add index to a column
    $table->index('column_name');
});
```

16. Dropping Indexes:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Drop index from a column
    $table->dropIndex('index_name');
});
```

17. Default Values:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Add default value to a column
    $table->string('column_name')->default('default_value');
});
```

18. Modifying Default Values:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Modify default value of a column
    $table->string('column_name')->default('new_default_value')->change();
});
```

19. Soft Deletes:
```php
Schema::table('table_name', function (Blueprint $table) {
    // Add soft delete column
    $table->softDeletes();
});
```

This cheat sheet covers the essential aspects of working with Laravel migrations. However, there are more advanced
