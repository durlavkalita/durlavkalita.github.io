---
layout: post
title: "flutter state management with provider"
date: 2021-06-09 11:54:49 +0530
categories: flutter
permalink: '/post/flutter-state-management-with-provider'
---

FLutter state management with provider 💻.

As I had mentioned before flutter state management has multiple options. The simple setState is good enough for small app and I get the hang of it but for medium and large app I need to learn one state management method. So, I started with `provider`. Created by flutter team provider is their recommended approach too(for beginners). So, let's see how provider works.

A/c to do flutter docs provider is - "A wrapper around InheritedWidget to make them easier to use and more reusable.".  So what is `InheritedWidget`? - "Base class for widgets that efficiently propagate information down the tree". Does provider is nothing but a parent which store state and passes it to children components (in simple terms). 

To use provider include it in `pubspec.yaml`. Provider uses `Notifier` to check changes/control state. Generally the notifier is in a higher parent widget so that state can be used in multiple children widget. The children widget use `Consumer` builder to display the state data. To change the state onTap or other events context.read() or context.watch() can be used.

Provider seems easy enough for now although there is much to learn. The official flutter docs provide good example for Provider and it is worth checking out.