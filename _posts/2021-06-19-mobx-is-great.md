---
layout: post
title: "Mobx is great"
date: 2021-06-19 11:54:49 +0530
categories: flutter state-management mobx
permalink: '/post/mobx-is-great'
---

Flutter state management with mobx 💻.

Mobx is a flutter state management approach. Recently I used provider for flutter state management and even bloc but both in a small scale. Coming from a vue background I really was looking for a state management which was simple and similar to vuex. Then I found out Mobx. It is not same as vuex but using it gives off the same easy vibe and also it is one of the popular way of state management in flutter.

The official [mobx site](https://mobx.netlify.app/getting-started) is great and you should visit it to learn it in depth. The documentation is very good. Mobx lets us create a store of data. Then we can reference that store class and use it for state management. There are three main concepts to understand here. The `observables` which are used to represent reactive data. The `actions` are used to change/mutate the observables much like actions in vuex. Lastly their is `reactions`. I have not gotten to it yet but in general they observe the observables and notify whenever there are some changes.

State management is something very important in flutter so, before choosing one, it helps to learn a bit about the popular ones. So, you should definitely give mobx a try.