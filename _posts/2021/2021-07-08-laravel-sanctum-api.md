---
layout: post
title: "laravel sanctum api"
date: 2021-07-08 11:54:49 +0530
categories: laravel sanctum
permalink: '/post/laravel-sanctum-api'
---

api authentication with laravel sanctum api.

One of the main requirement of any web app is a REST api. While building laravel app implementing a REST api is very easy thanks to sanctum package. sanctum package doesn't come by default on new laravel app but it can be installed using composer. The documentation about sanctum on laravel site is pretty good and easy to follow.

Sanctum can expose api's which are mentioned in the api.php file in laravel routes folder. These routes are normal routes just like written in web.php except they don't return a view but a json response. All methods such as POST, GET, PUT, DELETE are available. If any extra protection or functionality is needed they can be passed through a middleware.

Except for normal api auth sanctum has specific solution for SPA and mobile authentication. In case of mobile authentication laravel send a token to device when POST request is send to laravel for login. This token can be used to login to app from mobile platform. Sanctum thus provide a nice all round api for a laravel app and it's definitely worth using.