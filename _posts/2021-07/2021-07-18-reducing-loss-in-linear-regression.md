---
layout: post
title: "reducing loss in linear regression"
date: 2021-07-18 11:54:49 +0530
categories: ml linear-regression
permalink: '/post/reducing-loss-in-linear-regression'
---

Various ways to reduce the loss function in linear regression 💻.

Linear regression is one of the most basic ml algorithm. Represented as y=mx+c or y=wx+b, the main motive here is to find values of w and b for which loss function is minimum. The loss function is the (observation-prediction)^2. Now there are many ways to finding the loss function. Some of them are-

- iterative process- Here random (generally 0) values for w and b are considered and then from resultant prediction the loss function is calculated. As the main idea is to have the minimum loss function, the loss function is gradually reduced by considering values from that random point and observing whether their loss function value is increaing or decresing.

- gradient descent- Gradient is the derivative or partial derivative (in case there are more than one features) of a function. When the derivative value results as -ve then it means that we are going towards the decrease of the loss function. So by evaluating the gradient at a point we can get the idea that whether we are going in right direction(if its -ve) or not. Now only calcuating gradient at one point is not enough, we have to then increase or decrease it accordingly by a learning rate. Learning rate is a small step size which have to be multiplied with gradient magnitude to get the nest point in which we will calculate gradient. There is a goldilocks learning rate which determines the ideal learning rate value. Using this technique we can thus calculate the minimum loss function without using ranodm values.

- stochastic gradient descent- SGD is a technique where from a whole batch of data only 1 is selected to calculate gradient at one iterative step. It is used when the dataset is very huge.

- mini batch sgd - It is inbetween the above two step and instead of 1 10 to 1000 data's gradient are calculated from a whole batch.