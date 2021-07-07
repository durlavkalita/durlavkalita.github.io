---
layout: post
title: "json server"
date: 2021-07-07 11:54:49 +0530
categories: json-server npm REST
permalink: '/post/json-server'
---

Fake REST api using json-server {1️⃣}.

json-server is a npm package which creates fake REST api. Although there are servers like jsonplaceholder and others which provide a REST api, they are limited in power as the fields are already set and can't be modified. For a simple todo app these servers maybe enough but when there is a need of REST api with custom fields and values there is not much option out there. Also creating your own REST api for these purpose maybe helpful but it will take time and it might be an overkill.

json-server serves as a nice solution to this problem. It can be installed as a npm package globally. Then to create a REST api we just have to create a file db.json and inside it write the data in json format. Now running `json-server --watch db.json` will create your REST api @ localhost:3000. It is very simple and a nice example is given in its npm docs. Along with GET and POST, PATCH, PUT, DELETE routes are also available. When sending update or delete request the changes are persisted in db.json. This is only the surface level of json-server, in the docs how to use other route params are explained in details. So, when working with REST api using json-server might be a very good alternative to creating one from scratch. 