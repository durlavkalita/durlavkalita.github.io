---
layout: post
title: "Vue laravel and everything in-between"
date: 2021-06-24 11:54:49 +0530
categories: vue laravel
permalink: "/post/vue-laravel-and-everything-in-between"
---

Sending data from a vue component to laravel controller 💻.

I have been trying to make a dynamic form with vue. So once I finished it with the help of some old projects and the wonderful vuejs I thought about how to send the data to a laravel application. naturally being a dynamic form i have to transform the data to json which I did with `JSON.stringify()`. but now the problem is how to send it to laravel. I have to send the data to a laravel controller but things are not that simple.

First let's see how I would normally send the data. I would use fetch or axios and make a post request with the json data as payload. You would think that it should work. But the response from laravel is a 419 error. I am not sure if I'm totally correct but the only problem when a 419 error occurs is when there is no csrf token involved. So that's a new headache. How will I send a csrf token along with the data from vue to a laravel controller. Seems like many variables are involved. Maybe I should use ajax requests. So, I have to try different things till I find a good way. Until then Ah, shit here we go again.
