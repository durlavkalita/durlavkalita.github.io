---
layout: post
title: "image classification using keras"
date: 2021-07-15 11:54:49 +0530
categories: ml tensorflow keras 
permalink: '/post/image-classification-using-keras'
---

Training and testing image classification model using fashion mnist dataset 🎰.

Keras is a neural network library which works as a high level api for building neural networks. It is build on top of tensorflow. Keras as an api provides some methods to create layers of nn. I followed the tensorflow basic image classification tutorial to get started.

In order to use keras I created a new conda env with tensorflow installed in it. As it is build on tensorflow importing tensorflow is enough to work with keras. The dataset used for the neural network is the fashion-mnist dataset which is supposedly the hello world of nn. The dataset consists of images of 70000 grayscale fashion images in 10 categories. Now I had some previous knowledge of creating model and training and testing them using scikit learn, the creation of training and test dataset were familiar to me but while creating the model keras was used for the first time. Three layers were used- Flatten to flatten the images array from 2d to 1d , Dense layer of 128 nodes and another Dense layer of 10 nodes. The last layer would output the probabilty of each respective categories. At the end there was not much of keras involved but it was a easy first step in learning more about nn and tensorflow/keras api. 