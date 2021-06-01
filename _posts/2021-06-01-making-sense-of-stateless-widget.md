---
layout: post
title: "Making Sense of Stateless Widget"
date: 2021-06-01 11:54:49 +0530
categories: flutter
permalink: '/post/making-sense-of-stateless-widget'
---

Intro to my flutter journey. Making sense of stateless widgets from a web dev's view 🕸️💻.

It's been a few days of me working on flutter. Coming from a web background mobile dev with flutter feels odd but it is a lot easier once you know what are `Widget`'s. Web's main component are html tags cause that's what we see on screen. Similarly flutter's main component are `Widget`. Think of widget's as a html tag. You can add diffrent widget inside one. But widget's are much more than that. They can have parameters like a function and they can have their own state among other things. Perhaps Widget are like react or vue components. Anyway widget can have their own state and when they don't it's stateless widget.
  
Stateless Widget are generally used to display components which doesn't deal with chaging data. For eg.- To display facebook/twitter timeline in vue/react you create `Card` module to display each post data and display all posts using for loop of these cards. The `Card` module is what a stateless widget is. Infact `Card` is a widget in flutter. 
  
In a stateless widget you can add parameters like `Card(title,body,imgsrc)` and these value can be displayed in the widget but when these value changes the `Card` widget is deleted and a new `Card` is created with updated data so no state(data/information). I would love to write some code explaining stateless widget but they are already there at flutter site. Read more about it [here](https://api.flutter.dev/flutter/widgets/StatelessWidget-class.html). 