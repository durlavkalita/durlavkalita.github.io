---
layout: post
title: "laravel vue spa"
date: 2021-07-02 11:54:49 +0530
categories: laravel vue
permalink: "/post/laravel-vue-spa"
---

A SPA using laravel and vuejs💻.

Recently I have been looking for laravel and vue integrated system. Some previously wrote posts mentions about using laravel with jetstream livewire auth and vue components. Although that is a nice way to use both technologies, it doesn't fully realize the potential of vue as the app is not a full pledged SPA. Now SPA is single page application and it is popular as here the pages doesn't need to reload from page to page.

But come to think of it laravel and vue spa might be a nice thing. There is a package for it too. It's called laravel-vue-spa(shocker🤪). So how it uses the technologies? It uses laravel8 with vue + vuerouter + vuex + vuel18n + eslint preinstalled and configured. The vuel18n has to do with different languages. the package comes with authentication with jwt and other useful stuff and uses bootstrap for styling. The package is of course nice as it is a spa. But after using jetstream setup for so long it does seem a little odd to use this. The application uses laravel to generate api and uses them to show vue pages and components. Pretty neat. Using it should not be hard as controllers and all are same, only they don't generate a blade component but provides an api. More about it after I use this package.
