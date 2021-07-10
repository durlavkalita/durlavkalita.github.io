---
layout: post
title: "Persisting data in flutter 2"
date: 2021-07-10 11:54:49 +0530
categories: flutter data-persistance
permalink: '/post/persisting-data-in-flutter-2'
---

Persisting data in flutter using key value pair 📱.

As I had mentioned storing data using key value pair is very simple in laravel. Although it has some limitation about type of data that can be saved, for simple purpose like storing api token or user details(not password that would be risky) I don't think other methods are needed.

To use key value pair storage shared_preference package is used. To store data we have to get an instance of SharedPreference as `final prefs = await SharedPreferences.getInstance();`. Now to set data `prefs.setInt('variableName', value)` is enough. Ofcourse to store other datatype setInt will change to setString but that's about it. Similarly to get the data `prefs.getInt('variableName')` is used. Depending on the app these functions can be used anywhere but it is good to get initial data value in initState and update it accordingly later using set. 