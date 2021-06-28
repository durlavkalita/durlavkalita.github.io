---
layout: post
title: "Decoding Stateful Widget"
date: 2021-06-02 11:54:49 +0530
categories: flutter
permalink: '/post/decoding-stateful-widget'
---

Stateful widget is a flutter treasure and it's full of state 🎁.

Stateful widget's are rarely used flutter treasure. Mainly because most of the times displaying some ui is all that is needed and stateless widget does that. So why is Stateful widget? In a boilerplate flutter app you can see the counter example where with each button press counter increases. To perform these stunts where part of ui changes dynamically stateful widget is used. Now you can use a stateless widget but then you would need a stateless widget for button which when pressed have to update counter and send it to parent widget, then parent widget will update the counter stateless widget to show updated value. With stateful widget all these can be done within a single widget.

Ok, so let's decode a stateful widget. It extends of two classes rather than one class of stateless widget. One class is `StatefulWidget` class which is just like a stateless widget barring the `createState` method which is used to create the second class that extends `State` class. The first class is just like a stateless widget and it get's rerendered whenever state of the second class changes. The State class is where the state is stored (like the counter state). Whenever the state it it changes it replaces the first class with a new one having the updated state  of second class. So, second class is like a body and the first class is cloth (wow a nice analogy🤓). This state class of flutter stateful widget is a whole another thing. I will dedicate another blog entry for the state class. 