---
layout: post
title: "Tailwind for the win"
date: 2021-06-14 11:54:49 +0530
categories: css
permalink: '/post/tailwind-for-the-win'
---

Tailwind is the best css framework. Change my mind 🗣️.

We all love our css frameworks. From bootstrap, bulma to tailwind there are many out there and each of it has their own fanbase but I would like to make a case for tailwind to be the best for developers.

Tailwind CSS is detailed as "A utility-first CSS framework for rapid UI development". So, what does utility-first class mean? These are single purpose css class. For example in tailwind `bg-black` means `background-color: black` and nothing else unlike many other framework where a single classname can have multiple css behind it. Having this type of class helps a lot while developing. You just need to add the required class to your html element and they will behave exactly that you command, no need to understand if a class will affect other elements cause it won't.

There are some downside to tailwind, specially the fact that it has no ui component defined for table, form etc unlike bootstrap. It does mean that you have to write it out yourself improving your design skills and command over tailwind. Also there are sites like tailwindui which offer some predesigned responsive ui component. Another thing is as it uses utility based classes so, your element could have a very long list of class. The way around it is you can define them in `tailwind.config` file and use one single classname for all the classes. Read more about it in tailwind official site.

I really love using tailwind as it helps me focusing in building layouts and not worry about styling that much. I just need to use tailwind and add the required class on the fly with elements. Give it a try or perhaps you already do as it's great.