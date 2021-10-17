---
layout: post
title:  "Trying out pygame"
date:   2021-10-17 11:54:49 +0530
categories: python pygame
permalink: '/post/trying-out-pygame'
---

Finally tried out pygame. From creating browser based games using js predominantly I had no preconcieved idea of pygame but turns out it is intuitive and simple.

Much like canvas element in js, pygame creates a surface on which shapes can be drawn. The physics to control the created shapes is easily controlled by `move_ip()`. To create a game there also needs to be a game loop. The various key stroke events can be accessed from `pygame.locals`.

The best thing about pygame must be the concept of `sprites` which allows to control individual objects. Also using images instead of shapes and using sound in the game is easily done using sprites in pygame. Even though I am not interested in game dev but learning a new trick is always good specially when it is as easy as pygame.