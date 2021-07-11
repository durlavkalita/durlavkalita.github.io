---
layout: post
title: "Slopes and sigmoids"
date: 2021-07-11 11:54:49 +0530
categories: ml nn python
permalink: '/post/slopes-and-sigmoids'
---

Starting to learn ml💻.

I have started learning ml once again. I studied about the scikit learn library a few years back but now I wish to learn about tensorflow and pytorch in depth. So, naturally I started by watching some videos about basics of ml and nn to get myself upto speed.

One of the basic example of nn is the linear regression model. So what is linear regression? In simple terms it helps in creating relation between variables. Consider a straight line equation `y or f(x) = ax + b`. Here a is the slope or gradient of the line(vertical change/horizontal change) and b is the intercept on y axis. So, given the value of x, f(x) or y can be found. If we have a dataset of how y changes on different values of x them we can plot it in a graph and creating a line through the points in the graph we can estimate what will be f(x) for certain x and that's ml😄. But it is not very simple there are some things to consider.

- cost function - when we have multiple dataset it is impossible to have a straight line between them which intersects all the points. So, in that case how should one decide how to draw the line between dataset points? cost function is the sqaure of the value (prediction-real value). Suppose my straight line gives a y value of 20 for a x value 4 and the real dataset says it should be 19.5 so the cost function is .5^2 i.e .25. In ml the purpose is to get the lowest cost function so that the prediction is as precise as possible. Consider different cost dunction for different values of a and b (slope and intercept) we can model the data in a straight line function.

- slope - The slope or weight in ml of a variable is a measurement of effect of that variable on the final prediction. Slope can be found by calculating the derivative of the function. Slopes are generated randomly and by looping through different values we get the perfect weight or slope of a variable for which cost function is minimum. Similarly to the slope the optimal intercept value is also calculated from lowest cost function.

- sigmoid - sigmoid is a mathematical function, 1/1+e^(-x). The main characteristic of this function is it's value is always 0> and 1<. Thus using sigmoid we can limit the probability between 0 and 1 and depending upon what the model outputs as result we can see whether it's closer to 1 or 0 and make a predciction about the data.

I have just started learning ml so take what I wrote with a grain of salt as always. 