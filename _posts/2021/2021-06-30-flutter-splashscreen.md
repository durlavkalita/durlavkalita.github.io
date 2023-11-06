---
layout: post
title: "Flutter splashscreen"
date: 2021-06-30 11:54:49 +0530
categories: flutter
permalink: "/post/flutter-splashscreen"
---

Showing a splashscreen untill flutter app is loaded📱.

What is a splashscreen? Well whenever you open a mobile app like uber you see a screen with Uber written in black background only for the screen to disappear automatically after a few milliseconds. This screen is generally called a splashscreen. Splashscreen is used to show brand image or name until the app gets loaded.

So as I have mentioned splashscreen is pretty important specially when your app needs to load data from the first screen itself. Turns out flutter provides a default splashscreen. The code is initially commented out but some googling and fiddling with manifest and gradle files and you can show a splashscreen with flutter logo. The logo can be changed to your brand image. Besides the default splashscreen custom splashscreen can also be created. To know more about it follow advanced ui section in flutter docs. But beside these option there are some other hacks available too. Like the `Timer` widget which works like setTimeout. It can used to show the initial screen after a delay of a few seconds or milliseconds during which a temporary page can be shown which will act as splashscreen. Having splashscreen is although not necessary but provide a nice touch to a flutter app.
