---
layout: post
title: "FutureBuilder or async await"
date: 2021-07-13 11:54:49 +0530
categories: flutter
permalink: '/post/futurebuilder-or-async-await'
---

FutureBuilder and async await to work with api responses and future data 📱.

Working with api data most of the time we have to wait for the response from one endpoint and then perform some function on return data. Usually for these process js has promises and async await. In flutter as well using async await is a viable option but another option is the flutter's `FutureBuilder` widget.

FutureBuilder widget needs a `future` value which when available will build the `builder`. The builder method has two parameters the context and snapshot. Using snapshot methods like hasdata, haserror, data we can display various widgets conditionally. FutureBuilder will display the result in a new route once response arrives. A `CircularProgressIndicator` can be shown while the data/response is being loaded. the problem I found with FutureBuilder is the fact that it immediately displays the new route once response is ready giving me less control to do other task with the response like displaying a snackbar with response result.

So, I used the async await method instead and surely it gave me much more control. Instead of using futurebuilder when form submit is clicked I used the onPressed method with async function and using `functionName().then(result=>{})` I had the full control of what to do and display by writting code inside the curly braces. I was able to show a nice snackbar too with the onPressed method and thus all my requirements were fullfilled. The one problem with this approach can be that the route doesn't change untill it is told to do so inside the curly braces. So, no loading spinner can be shown(as far as I know) and if the api takes time to respond than app may seem like crashing. But all things considered this approach is much suitable for most of the cases. I think I will keep using this.