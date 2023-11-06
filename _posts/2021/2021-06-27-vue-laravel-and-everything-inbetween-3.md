---
layout: post
title: "Vue laravel and everything in-between 3"
date: 2021-06-27 11:54:49 +0530
categories: vue laravel
permalink: "/post/vue-laravel-and-everything-in-between-3"
---

Create your own dynamic form from JSON data using laravel💻.

I told how I was going to use vue to create a dynamic form JSON data. But there was a problem there. As the form would be dynamic I would have easily created the form but to store the input values of form with v-model would really suck. And then again I have to process all the data and send it back to laravel controller (which I know now how to do) and store in database. So, there would be a lot of work and so I thought about working with laravel blade component would be better.

The problem with blade component was that the data I was getting from the controller is a mixture of JSON, array and object meshed in a string. So, I did a lot of die and dump `dd()` and figured out how to separate the data in a way so that I would get the value required to create the form. And finally I succeeded. The good thing about laravel was I didn't had to use a bunch of v-model' s to store the data and then send it, I could do it directly in the action attribute of form itself and it made my life a lot easier. Now I am able to store the data as a string in database and a simple `json_decode()` function is enough to access the data in JSON format again. So, using laravel turns out pretty good. And it concludes my struggle to create a dynamic form using vue and laravel (finally).
