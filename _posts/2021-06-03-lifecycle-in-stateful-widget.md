---
layout: post
title: "What Stateful Widget is made of"
date: 2021-06-03 11:54:49 +0530
categories: flutter
permalink: '/post/what-stateful-widget-is-made-of'
---

Stateful widget and it's lifecycle ♻️.

In previous post I described about stateful widgets. It consists of two classes. The `StatefulWidget` class and the `State` class. As stateful widget have state so they have some lifecycle method. Lifecycle in general terms is an order in which different part of the code will get executed. So, let's see the statefull widget's lifecycle methods.

- createState() - `createState()` is from `StatefulWidget` class and it creates the second class `State`.
- build() - common in all widget. `build()` renders the ui.
- initState() - This is called when widget is created, after the constructor.
- didChangeDependencies() - It gets called when dependencies of the widget changes causing a new build.
- didUpdateWidget() - It gets called when state within `State` class changes and it needs to create a new Stateful Widget.
- setState() - This is used to set state and it causes a rebuild. It's similar to react's setState().
- deactivate() - It is called to move state from one point to another in the state tree.
- dispose() - It is called to destroy the state object.