## Twitter Clone

Demo Project of A Twitter Clone

### API Routes

```php
<?php

Route::get('/timeline', 'Api\Timeline\TimelineController@index');

Route::get('/tweets', 'Api\Tweets\TweetController@index');
Route::post('/tweets', 'Api\Tweets\TweetController@store');

Route::post('/tweets/{tweet}/replies', 'Api\Tweets\TweetReplyController@store');

Route::post('/tweets/{tweet}/likes', 'Api\Tweets\TweetLikeController@store');
Route::delete('/tweets/{tweet}/likes', 'Api\Tweets\TweetLikeController@destroy');

Route::post('/tweets/{tweet}/retweets', 'Api\Tweets\TweetRetweetController@store');
Route::delete('/tweets/{tweet}/retweets', 'Api\Tweets\TweetRetweetController@destroy');

Route::post('/tweets/{tweet}/quotes', 'Api\Tweets\TweetQuoteController@store');

Route::post('/media', 'Api\Media\MediaController@store');
Route::get('/media/types', 'Api\Media\MediaTypesController@index');

Route::get('/notifications', 'Api\Notifications\NotificationController@index');

```

### Web Routes

```php
<?php

use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('welcome');
});

Auth::routes();

Route::get('/home', 'HomeController@index')->name('home');

Route::get('/notifications', 'Notifications\NotificationController@index');

Route::get('/api/notifications', 'Api\Notifications\NotificationController@index');

Route::get('/timeline', 'Api\Timeline\TimelineController@index');

```
