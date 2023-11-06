---
layout: post
title: "Redesigning the site"
date: 2021-08-17 11:54:49 +0530
categories: blog tailwind
permalink: "/post/redesigning-the-site"
---

I have been meaning to redesign the site for quite some time now. But it is always a pain going through dribbble or template providing websites. There are so much option and although they may look easy to implement it will take some good amount of time to adjust it and code them for my site.

My site previously used sass to style the elements. Even though sass is very good I always preferred tailwindcss over any other css options. So that's what I did, removed every thing in `main.scss` except for pagination styling. Now in the barren html site I had the full control of redesigning. I though of adding the `tailwind.min.css` file in the blog folder but later decided to use the cdn. For the different elements rather than thinking about how to make them unique I borrowed the design from `blog.tailwindcss.com` and `tailwindui.com` sites. The former one is a blog site so it matches my site in that regard and tailwindui is an awesome site that provides free and paid tailwind components like hero section, footer etc to be used. Both sites used responsive design so it tackled another problem. Also I switched from dark to light background. I would sometime like to add theme changing option in the site but that will be a post for another day.
