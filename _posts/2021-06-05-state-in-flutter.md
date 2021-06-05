---
layout: post
title: "State in flutter"
date: 2021-06-05 11:54:49 +0530
categories: github
permalink: '/post/state-in-flutter'
---

I think I will use state, so what am I so afraid of, I'm afraid that I'm not sure of a state, there is no cure for 🎵.

State is important part of any web/mobile application. In general term state is collection of data of the app. Let's consider a todo app then the todos are it's state. For a blog posts, user data, comments etc are it's state. Coming from javascript background and using vuex(vuejs state management) extensively, I'm comfortable with the concept of state. But although there are a few similarities flutter state is quite different from vuex.

The low level approach is using `setState()`. I'm comfortable using it as it mimics reactjs's `setState()` in some degree. The only problem is for a large level app it will get messy. If you are getting data from api then you surely don't wanna use setState(). It is good for forms and low level data storage. Using `InheritedWidget` also falls in this category. In `InheritedWidget` data is transfered from top/parent to children level.

The better approach for a large application is a state management system. Unfortunately vuex is not compatible with flutter(I guess). As a state management system there are probably three main options. `Redux`, `BLoC`, `MobX`. Now I can't comment on any of them as I am still learning. But in general Redux is developed by facebook and is used in Reactjs app generally. Bloc is from google and I'm learning about it and MobX seems a popular third options. Once I use all three of them then maybe I will compare them.