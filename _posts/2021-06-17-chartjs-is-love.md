---
layout: post
title: "Chartjs is love"
date: 2021-06-17 11:54:49 +0530
categories: chart laravel javascript
permalink: '/post/chartjs-is-love'
---

Creating charts is gonna be my new thing 💻📈.

As I mentioned I was trying to include charts in a laravel project. The laravel package made using chartjs was not properlly working for some reason. So, I went and tried chartjs and I loved it.

Normally I don't like to include js in a laravel project unless it's necessary. But using chartjs was very easy. I am using it through the cdn and it works fine. The chartsjs library is pretty neat. To introduce a chart just add a `canvas` element and in js get the element by id and get it's context similar to how canvas is normally used. The fun starts in `Chart()` function. There you can specify the chart type, give it's data and tweak with it's color/border and axis options. I would definately recommend using it for any charts you may want to show in your site.   