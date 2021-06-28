---
layout: post
title: "Mobx and provider"
date: 2021-06-20 11:54:49 +0530
categories: flutter state-management mobx provider
permalink: '/post/mobx-and-provider'
---

Mobx store with provider state is the way to go🚞.

So, I have been using mobx since yesterday and it has been smooth sailing till now. But during a tutorial I found out that you could use provider with mobx and this changes things.

The basic concept of mobx is simple. Create a store. Define the observables or computed values, actions and reactions(if it is there). Once it is done import the state in `main.dart` and use the Class and `Observer` widget to check if the state changes. Very simple. But instead of defining the class in main.dart to use it, we can use provider to lift the state. So, you now wrap the root build() function with `Provider<T>` where T is the store/class name. And whenever we need to access the store from a child we can use it by `Provider.of<TodoList>(context)`. It may sound a bit confusing but if you follow the mobx site guide you will see what I am talking about. Learning provider is something I wanted to do and now as both provider and mobx works well with each other I think I have found a winner for my flutter state management dilemma.