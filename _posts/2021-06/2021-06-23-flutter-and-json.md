---
layout: post
title: "Flutter and json"
date: 2021-06-23 11:54:49 +0530
categories: flutter json 
permalink: '/post/flutter-and-json'
---

flutter json and all the serialization💻. 

Working with json is a necessary part for every app and flutter is no different. In order to use all the api's of world and for own backend we need to work with json but it's not very straight forward in flutter. As flutter cannot directly use json data. We have to do something called `serialization` with it. So what is serialization. It is the process of converting json data to dart data and vice versa(in simple terms).

There are two types of serialization manual and automated. In automated we have to use third party packages and it is suitable for large apps. But manual is writting the the whole process with models and jsonDecode() function. I seem to get the hang of manual serialization atleast for now.

In manual serialization first step is creating a model class for eg.- class User or class Post etc. Once the model class is defined, use `Model.fromJson()` to create a new instance of model and  `toJson()` to convert the Model instance to a map.  The `jsonDecode()` function can be used to get a model value from it's json and `jsonEncode()` for the opposite. Now there is much more to it but it is a good start to manual json serialization in flutter.