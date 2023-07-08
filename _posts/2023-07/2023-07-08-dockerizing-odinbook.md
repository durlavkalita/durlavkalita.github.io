---
layout: post
title: "dockerizing odinbook"
date: 2023-07-08 11:54:49 +0530
categories: odinbook docker
permalink: "/post/dockerizing-odinbook"
---

Dockerizing odinbook.

I always liked docker. It's easy to use and benefits are clear. Of course I am by no means a docker, but dockerizing the odinbook project was easy enough. I have to admit I haven't worked on the project for a while now and it all comes down to frontend. Meaning I only have to make the frontend nice right now for the most part and that can be tedious.

Anyhow I started with backend first. I found this [link](https://nodejs.org/en/docs/guides/nodejs-docker-webapp) on official nodejs site to dockerize an app and it worked perfectly well. Just instead of using main nodejs image use nodejs:alpine image. It saved me around 1.5 gb of space. The image is of 229 mb size. For frontend the process is same I guess that's one of the perks of using javascript as the whole stack.

Once these two were created I created one docker-compose file to combine both of the dockerfile. The result unsurprisingly is the same. The only thing is I am not quite sure how to use environment variable. Also here I have not used a local database so If that has to be added then I guess the dockerfile will change. But that's a topic for later discussion.
