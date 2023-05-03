---
layout: post
title: "Flutter navigation"
date: 2021-06-06 11:54:49 +0530
categories: flutter
permalink: "/post/flutter-navigation"
---

Navigating through the wonderful and full of widget flutter 📱🚇.

Navigation in a app is moving from one page/screen to another with or without passing data. Flutter navigation is actually quite easy to understand (at least easier than state in my opinion). Flutter has a widget called `Navigator` which makes life easier for us. Navigator has two basic function pop() and push(). Both are self explanatory. In flutter unlike web navigation works like a stack. So, you have a home screen at `'/'` and another screen at `'/another'`. So, the stack will have home screen initially. Once you push the `'/another'` route it will add it on top of `'/'`. In order to get back to home route from another route you just need to pop that route.

Now you can only go so far with pop() and push() method. In large application it is needed to add name for each route so that you don't repeat code. For named route flutter has pushNamed(). Here along with context you provide the route name and it takes you there. And returning is again done by pop() method.

In order to pass arguments with route you just need to define the arguments to pass and pass the argument as parameter in pushNamed() method. You will need `ModelRoute.of()` to extract the arguments. Returning data from new screen to old screen can be done in the pop() method. And knowing these few methods is all you need to navigate in a flutter app. To experiment and know more about go to [flutter navigation docs](https://flutter.dev/docs/cookbook/navigation) and you will realize how simple it is.
