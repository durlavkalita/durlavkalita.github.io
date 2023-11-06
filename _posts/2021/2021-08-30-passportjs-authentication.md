---
layout: post
title:  "Passportjs authentication"
date:   2021-08-30 11:54:49 +0530
categories: auth passportjs nodejs
permalink: '/post/passportjs-authentication'
---

It's been a long week of understanding authentication and I think I have got the hang of it now. It prev post I described how jwt can be used and this time another important topic i.e. passportjs.

Passportjs is middleware. So you give it a input and it will do something and then call `next()`. Now passportjs has different strategies. Strategies are different way of providing authentication and authorization. We can implement facebook, google, github auth using differant passport strategy. But the most basic and my need was for passport-local and passport-jwt.

passport-local- strategy takes in username and password field as input. From the input we can find user or add user to database. After importing passport and passport-local we can implement a basic user signup like this.
```
passport.use(
    'signup',
    new localStrategy(
      {
        usernameField: 'email',
        passwordField: 'password'
      },
      async (email, password, done) => {
        try {
          const user = await UserModel.create({ email, password });
  
          return done(null, user);
        } catch (error) {
          done(error);
        }
      }
    )
);
```
We can add this `signup` strategy as a middleware in our route.
```
router.post(
  '/signup',
  passport.authenticate('signup', { session: false }),
  async (req, res, next) => {
    res.json({
      message: 'Signup successful',
      user: req.user
    });
  }
);
```
Pretty simple. When we visit `/signup` route and submit the data it will invoke the `signup` strategy defined above and add new user to database. The session object is for whether to use store data in express session and is you can read more about how to use in passprtjs site.

passport-jwt- Now this is what I wanted to know and is very useful. Here in the strategy we extract a token from Header or as query parameter. Then this token is used to check if the user is valid. Token is only given to user who are loggedin so only authenticated user will have token and thus will pass this middleware and get the user data. The secretOrKey value passed here is any random value which should be used as env variable for security.
```
passport.use(
  new JWTstrategy(
    {
      secretOrKey: 'secret',
      jwtFromRequest: ExtractJWT.fromAuthHeaderAsBearerToken()
    },
    async (token, done) => {
      try {
        return done(null, token.user);
      } catch (error) {
        done(error);
      }
    }
  )
);
```
Now like before in any route where we want auhtentication we can add-
```
router.post(
  '/profile',
  passport.authenticate('jwt', { session: false }),
  async (req, res, next) => {
    res.json({
        user: req.user
    });
  }
);
```
So now we can visit `\profile` route and it will check whether token sent to the route is valid or not and then provide access to the route.

This is the simplest implementation of passport and jwt that can be used and it works well for me. Ofcourse there are many things that can be added for auth and for that google is our friend. 