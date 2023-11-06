---
layout: post
title: "Vue laravel and everything in-between 2"
date: 2021-06-26 11:54:49 +0530
categories: vue laravel
permalink: "/post/vue-laravel-and-everything-in-between-2"
---

Sending data from a vue component to laravel controller is simple💻.

So, a few days ago I wrote how I could not figure out how to send from vue to laravel controller. Seems like there was no major problem there. Whether you use axios or fetch or any other options the data gets send to the route specified. You can confirm that by console logging the status or response. My problem was I was not storing the data in database inside the controller rather was just die and dumping it. But using Request $request object retrieving the sent value can easily be accessed and stored and that's how you send data from vue to laravel controller.

But the solution is only half done. In order to use the data we can easily send it to either vue or blade components. The main problem occurs with the data type. The data sent from vue component gets stored as a string. Now that string is actually a list which has several objects inside them. So, handling the data gets messy. I am still working with the data. I have gone ahead and used vue as javascript provides more options while working with these peculiar JSON types.
