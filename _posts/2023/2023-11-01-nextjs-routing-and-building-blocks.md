---
layout: post
title: "nextjs routing and building blocks"
date: 2023-11-03
categories: nextjs
permalink: "/post/nextjs-routing-and-building-blocks"
---

Continuing nextjs.

In Nextjs one major difference in initial file/folder structure was in `app` directory. Nextjs doesn't need a react-router type library, it handles routing by creating directories inside `app` directory. For example- `/app/blog` will create a `/blog` route and `/app/blog/[slug]` will create a route for each posts as `/blog/slug`. Pretty unique and you can say it's better when you consider files you can put inside a directory. Continuing our example directory we can add -

- app
  - page.tsx -> Home Page
  - layout.tsx -> Provides base UI and preserves state
  - blog
    - page.tsx
    - [slug]
      - page.tsx

Other than `layout.tsx` there are `error.tsx`, `not-found.tsx` etc and for directory names [...name], [[...name]] etc can be used all of which provides different functionality. Till now I have only used `layout.tsx` and `page.tsx` but even I can appreciate how convenient all these can be.

What else, oh `Link` tag is different here. I have used `Link` tag of react-router library so I am familiar with the concept but still it felt a bit different as well as use of `Image` tag which I felt hostile in nature just cause I had to provide `width` and `height` property to it everytime. I generally have no complaint regarding the routing till now, yes the methods are different but understandable. Next I am going to learn about data fetching. BDW declaring `use client` in a page will let us treat a file same as a react file so that's nice. When using hooks not using `use client` will throw errors.
