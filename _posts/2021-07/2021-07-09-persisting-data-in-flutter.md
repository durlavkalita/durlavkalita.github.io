---
layout: post
title: "Persisting data in laravel"
date: 2021-07-09 11:54:49 +0530
categories: flutter data-persistance
permalink: '/post/persisting-data-in-flutter'
---

Persisting data in flutter by different methods 📱.

Persisting data is important for any web or mobile app. While building app using flutter, there are a few ways data can be persisted in the system. We can use a sqlite database to save data, use the file system to read or write data into a file in file system or use simple key value pairs.

To use a sqlite database a package called sqflite is used. It works as a normal database, crud operation are allowed in the database and a model has to be there for the data. This system is nice when there is a large amount of data. But I havn't yet figured out where the sqlite database is stored probably on the mobile memory somewhere. When using file system to dave data, path_provider package is used to access device file system. The data can be saved on cache as temporary or on a permanent directory created with the app. the implementation is easy enough but I couldn't test it maybe because I was using flutter web. The last one i.e. key value pair works nicely on flutter web too. It persists data upon reload but not upon termination which is supposed to happen. Here we don't need file system access rather we use shared_preference plugin which wraps platform specific widgets and provide way to store data as key value pairs. But using these only int, bool, double, string and stringList type can be saved. So, although it is very simple there is trade off and ofcourse safety of data stored has to be considered as well.