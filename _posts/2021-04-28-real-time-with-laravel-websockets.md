---
layout: post
title:  "Real time with laravel-websockets"
date:   2021-04-28 11:54:49 +0530
categories: laravel websockets
permalink: '/post/real-time-with-laravel-websockets'
---

Laravel is the most popular php framework and rightfully so. Using laravel and it’s MVC model to create a simple blog or web app is very easy to learn and intuitive in nature. But how to implement a real time, live-updating user interface in laravel. That’s where laravel-websockets comes in.

In order to work with real time projects in laravel you have to have a basic knowledge of [broadcasting](https://laravel.com/docs/8.x/broadcasting) and [events](https://laravel.com/docs/8.x/events).

- Step 0-
  Let’s start with a fresh installation of laravel. Also setup and configure database for the application.
  ```
  laravel new laradiy
  cd laradiy
  ```
  <br/>
- Step 1-
  Now let’s install laravel-websockets. You can follow their [official documentation](https://beyondco.de/docs/laravel-websockets/getting-started/installation) for detailed info or run the following commands.
  ```
  composer require beyondcode/laravel-websockets
  php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="migrations"
  php artisan migrate
  php artisan vendor:publish --provider="BeyondCode\LaravelWebSockets\WebSocketsServiceProvider" --tag="config"
  ```
  <br/>
- Step 2-
  Now we have to make some changes in the application. For broadcasting event laravel-websockets uses [pusher](https://pusher.com) and it’s api. Pusher provides an excellent and friendly choice for real time technology for reasonable price.
  `laradiy/.env`
  ```
  // remove this line
  BROADCAST_DRIVER=log
  // add these line
  BROADCAST_DRIVER=pusher
  PUSHER_APP_ID=12345         // random numbers
  PUSHER_APP_KEY=QWERTY       // random string
  PUSHER_APP_SECRET=ASDFGH    // random string
  ```
  What we did is changed broadcast driver to pusher and gave some random value to identify the pusher server. The data or event we are going to send won’t go to pusher server but will go to laravel-websockets server, which is our own server.
  ```
  php artisan serve
  php artisan websockets:serve
  ```
  Go to [localhost:8000](https://localhost:8000/), you will see laravel boilerplate app. Now go to [localhost:8000/laravel-websockets](https://localhost:8000/laravel-websockets), you will see the laravel-websockets dashboard. Click on connect and you will notice the some events. Voila your server is ready to listen for events. Now let’s send an event to our server.
  <br/>
- Step 3-
  Now our server is ready and in order to broadcast events let’s install pusher.
  ```
  composer require pusher/pusher-php-server "^5.0"
  ```
  Now we have to configer `config/brodcasting.php` file so that the events gets sent to our own server at localhost:8000/laravel-websockets.
  ```
  'pusher' => [
    'driver' => 'pusher',
    'key' => env('PUSHER_APP_KEY'),
    'secret' => env('PUSHER_APP_SECRET'),
    'app_id' => env('PUSHER_APP_ID'),
    'options' => [
        'cluster' => env('PUSHER_APP_CLUSTER'),
        'host' => '127.0.0.1',
        'port' => 6001,
        'scheme' => 'http'
    ],
  ],
  ```
  <br/>
- Step 4-
  Now to check if it’s working let’s create and send an event.
  ```
  php artisan make:event NewEvent
  ```
  In `app\Events\NewEvent.php` modify the new event class-
  ```
  class NewEvent implements ShouldBroadcast
  {
    use Dispatchable, InteractsWithSockets, SerializesModels;
    public $msg;
    public function __construct($msg)
    {
      $this->msg = $msg;
    }
    public function broadcastOn()
    {
      return new Channel('home');
    }
  }
  ```
  What we did is just added `ShouldBroadcast` to brodcast the event. The event will accept a `$msg` string parameter. Run `php artisan tinker` . In the tinker terminal create an instance of `NewEvent` -
  ```
  event(new App\Events\NewEvent('hello'))
  ```
  So, now your server is running and it is listening for any event triggered. Now let’s propagate the event and `$msg` to the client side with laravel-echo.
  <br/>
- Step 5-
  In order to listen for the events we need laravel-echo. Also as we are using pusher for broadcasting we need pusher-js. Let’s install those.
  ```
  npm install --save-dev laravel-echo pusher-js
  ```
  Now we have to configure laravel-echo in `resources/js/bootstrap.js` .
  ```
  import Echo from 'laravel-echo';
  window.Pusher = require('pusher-js');
  window.Echo = new Echo({
    broadcaster: 'pusher',
    key: process.env.MIX_PUSHER_APP_KEY,
    cluster: process.env.MIX_PUSHER_APP_CLUSTER,
    forceTLS: false,
    wsHost: window.location.hostname,
    wsPort: 6001
  });
  ```
  Most of the lines are already there just un-comment it and add wsHost and wsPort details. Compile the changed js by-
  ```
  npm run dev
  ```
  <br/>
- Step 6-
  Alright everything set let’s view it in browser.
  `resources/views/welcome.blade.php`
  ```
    <script>
    Echo.channel('home').listen('NewEvent', (e) => {
      console.log(e.msg);
    })
  </script>
  ```
  So, we are using app.js. As we have access to Echo, we are listening for `NewEvent` event in the `home` channel. When that event gets triggered we will log the msg that was sent with the event. Run `php artisan tinker` In tinker again trigger the event.
  ```
  event(new App\Events\NewEvent('hello'))
  ```
  You will see hello printed in the console window of [localhost:8000](https://localhost:8000/).
<br/>
<br/>
In general writing javascript in blade component is not a good idea. So, you should write the javascript code in your `resources/js/app.js` . In order to use echo just add `window`. before the lines. For eg.-
```
window.Echo.channel('home').listen('NewEvent', (e) => {
console.log(e.msg);
});
```
And then compile your javascript by -
```
npm run dev
```
This should work just as fine.
<br/>
<br/>
So this is how you can setup laravel-echo for real time application in laravel. You can also use socket.io with laravel but with laravel-websockets you don’t need to dive in other technologies beside php. To learn more about this topic you can go through the following links-

- [Laravel-websockets](https://beyondco.de/docs/laravel-websockets/getting-started/introduction)- Official documentation.
- [Broadcasting](https://laravel.com/docs/8.x/broadcasting)- Broadcasting events in laravel.
- [DevMarketer](https://www.youtube.com/watch?v=pIGy7-7gGXI)- Video about setting up laravel-websockets.
- [QiroLab](https://www.youtube.com/playlist?list=PL1TrjkMQ8UbWfFUCimQ50CdrR_J7QvEFW)- Video series about creating chat app using laravel-websockets.
- [github](https://github.com/durlavkalita/laradiy)- Github repo of the code.