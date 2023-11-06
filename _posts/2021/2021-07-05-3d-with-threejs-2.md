---
layout: post
title: "3d with threejs 2"
date: 2021-07-05 11:54:49 +0530
categories: threejs javascript
permalink: '/post/3d-with-threejs-2'
---

Threejs gives you wings(3d wings) 🐦💻.

So I took a deep dive into threejs today and now I have some idea on how to proceed. As mentioned in earlier posts, threejs uses a scene to where graphics is rendered, a camera which is used as a POV and a renderer to render the scene. So scene is where we can draw different shapes. There are various geometry objects which can be used to construct a shape, and there are materials which works as a wrapper around the geometry. These two meshed together when added to scene object will create a static 3d graphic. And then there are types of light which when added to scene enables us to see an object. In order to display a graphic, render function is used in which scene and camera are passed as arguments.

So it seems the basic are knowing how to use scene, camera and renderer in threejs then according to a specific design we can use various threejs functions available in it's doc to create whatever we want.