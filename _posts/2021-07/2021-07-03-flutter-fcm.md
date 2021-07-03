---
layout: post
title: "flutter fcm"
date: 2021-07-03 11:54:49 +0530
categories: flutter firebase fcm
permalink: '/post/flutter-fcm'
---

Send notification to flutter app with the awesome firebase fcm 📱.

Flutter is nice and it gets even better when used with firebase. Why? maybe both are google products that's why. But on a serious note firebase itself is a great product and I hope to learn and use it more in future. Firebase can be used as a database or for auth in flutter app among other things. Recently I used firebase with flutter for a notification system.

So, there is this awesome feature in firebase called fcm or firebase cloud messaging. It can be used to send message or notification to app either web or mobile. And as it happens integrating a flutter app with fcm is not that dificult, although most of the documentation are not very straight forward too. Anyway I will talk more about the technical part of it later. The notification in a mobile app can be of three types. When app is running, when app is not running or in background and I forgot the other one. For each case we have to listen for incoming messages and work accordingly. There are Future data type involved all over. Flutter has some nice packages for working with fcm. If you want to use it in your app I would recommend watching a recent video about it on youtube. Reading the documentation is always better but I found it a bit confusing so I took the other route and now I am sending notifications at will🎩.