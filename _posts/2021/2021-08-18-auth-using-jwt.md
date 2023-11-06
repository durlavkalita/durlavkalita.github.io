---
layout: post
title:  "Auth using jwt"
date:   2021-08-18 11:54:49 +0530
categories: auth jwt nodejs
permalink: '/post/auth-using-jwt'
---

Authorization is perhaps the most important and difficult part of any web app. Different framework handle authorization differently. Unlike some other framework where authorization scaffolding is provided, in nodejs authorization has to be done manually and that's where jwt comes in.

jwt stands for jason web token. As the name suggests implementing jwt in node app provides a token for individual user which can be used to verify them and provide access to specific routes. To use jwt in node app we have to first install jsonwebtoken npm module by `npm i jsonwebtoken`. We can import jsonwebtoken by running `const jwt = require('jsonwebtoken');`. Now jwt has two main part `sign` and `verify`. We have to first sign the user data to get a token and then we can use verify later to check whether if the token is correct or not.

- jwt.sign()-
  jwt.sign should be used while logging in a user. A simple format for using jwt.sign is -
  ```
    jwt.sign({user}, 'secretkey', {expiresIn: '600s'}, (err,token)=>{
        res.json({
            token
        })
    });
  ```
  The first parameter is the user data. The user data can be retrieved from a login form. Second parameter is the secret key that can be any string and should be accessed from .env file. The next parameter is for various options here I have included the expiresIn option to indicate how long a token should work. Then a callback function which will return a the token generated. This token should be saved in localStorage of browser for future uses.

- jwt.verify()-
  jwt.verify is used to verify if the token provided is correct which will mean that user is authenticated. The general format is-
  ```
      jwt.verify(req.token, 'secretkey', (err,authData)=>{
        if(err) {
            res.sendStatus(403);
        } else {
            res.json({
                msg: 'access granted',
                authData
            })
        }
    });
  ```
  Here the first parameter is the saved token(I have assumed that token is saved in req.token). Then the secret key and callback function. To protect routes a middleware function has to be implemented in the route. The token saved in localStorage can be passed as route request header(req.header) inside the middleware. From there the request header can be accessed and req.token can be set to that token in the header.

This is just a brief implementation of jwt that I seem to understand easily and there are other ways to implement it  as well. Also jwt and passportjs can used together to make more robust auth system.

Check out the following links for more info-
[jwt github](https://github.com/auth0/node-jsonwebtoken)
[jwt implementation video](https://www.youtube.com/watch?v=7nafaH9SddU)