---
layout: post
title:  "A nice box shadow"
date:   2021-05-23 11:54:49 +0530
categories: css
permalink: '/post/a-nice-box-shadow'
---

Now I've heard there was a secret css, that Durlav used, and it pleased the Blog, But you dont really care for styling, do you? 🎵🎼

Sorry for ruining Leonard Cohen's Hallelujah🤤, but right now if you hover over my navigation menu items, you will see a nice hover effect. Although a few things are happening there, the main ingredient there is the box-shadow effect. When I was creating the site, insted of creating my own box-shadow effect I searched the internet for it (as a good developer😏) and I found one at [getcssscan.com](https://getcssscan.com/css-box-shadow-examples). So, let's see what is happening behind the scenes in that box-shadow.

The code for the box-shadow is-
```
box-shadow: rgba(240, 46, 170, 0.4) -5px 5px, rgba(240, 46, 170, 0.3) -10px 10px, rgba(240, 46, 170, 0.2) -15px 15px, rgba(240, 46, 170, 0.1) -20px 20px, rgba(240, 46, 170, 0.05) -25px 25px;
```

The general syntax of box-shadow is-
```
box-shadow: [horizontal offset] [vertical offset] [blur radius] [optional spread radius] [color];
```

What is happening in the code is, it is creating 5 different box-shadows separated by commas. With each box shadow the rgb composition is same (240, 46, 176) but the alpha(a) or opacity value is gradually decreasing giving distinction to the color of multiple levels. Also with every box-shadow the horizontal and vertical offset are increasing giving the nice multilayer effect.