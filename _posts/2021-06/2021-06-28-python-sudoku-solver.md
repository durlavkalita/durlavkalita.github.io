---
layout: post
title: "Python sudoku solver"
date: 2021-06-28 11:54:49 +0530
categories: python sudoku
permalink: '/post/python-sudoku-solver'
---

I have always loved solving sudoku and I love python, so it's only fair to combine both 🏁💻.

For some days I was getting youtube recommendation for a video by computerphile channel. It's called [python sudoku solver](https://www.youtube.com/watch?v=G_UYXzGuqvM). Having interest in both topics I finally watched the video and shocker they used recursion🤓.

The first step was creating a function which given x,y axis value and a number n can determine whether n can be inserted in the (x,y) position in grid. It is pretty straight forward. The solve() function is where we loop through all the squares in the grid and execute the first function to see which number fits in that square. Recursion is used in the solve() function so that once one square is filled we don't loop through that sqaure again. Pretty neat huh. It is explained in the video wonderfully.

A few days ago I came across the fib method that can be used to reduce time complexity of a recursion function. I will write about that function someday but I wonder if the above solution can be made more efficient with that method. Now that I think of it, the answer is probably not. Yeah, fib method should be explained before discussing more about it.