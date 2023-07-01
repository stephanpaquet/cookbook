```php
//routes/web.php
Route::get('/post/{post}', 'PostsController@show');

//PostsController.php
public function show(Post $post) {
    return view('posts.show', [
        'post' => $post
    ]);
}
```
So when I went to URL **_/post/1_**, the Post with id 1 was available inside the controller as variable $post. I didn’t had to fetch myself anything from the Database. If I entered a URL with id that did not existed in the Database, I was even redirected to a 404 Page

## Implicit Model Binding
While we’ve seen explicit model binding, here’s an example of implicit model binding now:

```php
Route::get('posts/{post}', function (App\Post $post) {
    // be awesome. enjoy having the $post object
});
```

## Changing the Model’s Route Key
If you would like the implicit model binding to use a database column other than id when retrieving models, you may override the getRouteKeyName method on your Eloquent model.

For instance, if we wanted to use the slug instead of the id, we could do the following:

```php
class Post extends Model {
    public function getRouteKeyName() {
        return 'slug';
    }
}

```
Then we could access our route using http://awesome.example.com/posts/my-post-slug instead of http://awesome.example.com/posts/24.

