---
layout: post
title: "Vuejs and laravel 2"
date: 2021-06-22 11:54:49 +0530
categories: laravel vuejs
permalink: "/post/vuejs-and-laravel-2"
---

vuejs with laravel and livewire gives you wingsss 🐦🐦.

As I had mentioned yesterday I was looking to use vuejs in a laravel application along with blade components. I listed three options that I had and it turns out that the first option is good enough for me. I really like the jetstream package provided by laravel so I didn't want to use laravel/ui package. I thought about using inertia but inertia stack is not something I am familiar with. So, the most logical choice was using jetstream with livewire-blade stack. It will give me a nice boilerplate with blade components and livewire which I am accustomed too. Then the main task was installing vue and seeing if it will work.

I installed vue using npm and modified the webpack.mix.js file accordingly. As it turns out using vue is pretty simple. I just then have to create a vue file and declare it in app.js and run npm run dev. The vue component will be then shown inside the div element with id of app. So now I will use blade and livewire for normal work and vue component whenever there is a need of more reactive element.
