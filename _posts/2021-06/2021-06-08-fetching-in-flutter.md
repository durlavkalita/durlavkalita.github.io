---
layout: post
title: "Fetching in flutter"
date: 2021-06-08 11:54:49 +0530
categories: flutter
permalink: "/post/fetching-in-flutter"
---

Fetching data from api's in flutter 📗.

Fetching in web is done by either `fetch` or `axios`. In flutter fetching data from internet is done with the help of `http` package. Include it in `pubspec.yaml` and run `flutter pub get`. Just like fetch in web, in flutter we use `http.get('url-address')`. The fetching process will not produce immediate result but in future so, the return data type to be used is `Future`. Also using async-await is applicable here too.

One thing to note here is many times the api returns a json value and we have to convert it to dart object for that read about JSON serialization in flutter site. Lastly calling an api should be performed in initState() not in build() as build() gets called very often in flutter.
