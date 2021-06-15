---
layout: post
title: "FLutter folder structure"
date: 2021-06-15 11:54:49 +0530
categories: flutter
permalink: '/post/flutter-folder-structure'
---

Organizing dart files in flutter app the right way 💻📁.

Unlike frameworks like react or vue, flutter folder structure is not very descriptive. Yes there is `main.dart` file in `lib` folder and all the code belongs to that folder but due to lack of a huge community like javascript or other reasons it is not well documented how should I structure my app folders. As I have been working on flutter and been looking at flutter code on the web recently, I have a vague idea how you should structure a flutter app.

As with all programming languages, following 'dry' principle is a good idea and for that component should be divided into modules. For example you can have a textfield.dart file for any input textfield and later use it in a login/register form. You should generally have them in a `lib/widgets` folder.

If the app consists of multiple screen's like login, dashboard,profile etc then there should be a folder as `lib/screens` for them.

For the various helper functions a folder like `lib/helpers` or `lib/utilities` might help.

In dart we have to transform json data to dart classes to use them as json is not supported. So for all these a folder like `lib/models` is a nice place.

For firebase or database integration a folder like `lib/services` might come in handy.

As I have not yet used state management on flutter till now I won't comment on how that should be structured but I will write about state managment once I get the hang of it.