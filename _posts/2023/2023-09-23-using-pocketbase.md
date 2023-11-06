---
layout: post
title: "using pocketbase"
date: 2023-09-23
categories: pocketbase react
permalink: "/post/using-pocketbase"
---

Finally used pocketbase as backend.

In recent years firebase, supabase and pocketbase has been in the rise. Firebase was there long before the other ones and I have used it previously but I was really looking forward to using either supabase or pocketbase for a project. As far as I know supabase is more similar to firebase in that you have to use their platform just like firebase and has additional features(as far as I understand). Pocketbase on the other hand lets you download it's executable and by running it you can have your own backend locally. Ok, let me go into some depth.

When using a nodejs backend you are typically running `npm run dev` on your local machine which in turn exposes api endpoints for **CRUD** or other operations. In case of pocketbase there is a similar command `pocketbase serve` in the extracted pocketbase directory will start the service on port `8090`. There after logging in we get a dashboard where we can create tables and define relationships and other things we require from a backend/database.

Now when connecting it to the frontend, in case of a nodejs backend we may make a _GET_ or _POST_ request to `localhost:3000` or something but in case of pocketbase we can use the [web api references](https://pocketbase.io/docs/api-records/) to look for what we need and implement it.

```javascript
// using nodejs backend
const record1 = await fetch("http://127.0.0.1:3000/posts").then(
  (response) => {}
);
```

```javascript
// using pocketbase
import PocketBase from 'pocketbase';

const pb = new PocketBase('http://127.0.0.1:8090');

...

const record1 = await pb.collection('posts').getOne('RECORD_ID', {
    expand: 'relField1,relField2.subRelField',
});
```

Pretty neat specially for someone who doesn't want to write backend for a simple frontend project. In my case I just wanted to see how pocketbase works so I created a chat app with **react** as frontend and used **pocketbase** for `users`, `messages` table. Pocketbase offers realtime api too which is great for this type of app. I followed the [firebase](https://fireship.io/lessons/pocketbase-chat-app/) article on using pocketbase to create a chat app. The article used **svelte** but the pocketbase implementation code remained same just like a real backend service would.
The code for my app is [here](https://github.com/durlavkalita/react-pocketbase-chat-app). I will have to make some tweaks though. Seems like you don't use react for about a month and it's all gone from my brain.
