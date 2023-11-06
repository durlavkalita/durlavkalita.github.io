---
layout: post
title: "trying out pagination"
date: 2023-11-06
categories: reactjs nodejs pagination
permalink: "/post/trying-out-pagination"
---

Pagination or infinite scrolling.

I wanted to change somethings in my Odinbook project. Well change is not the right word maybe just ork on it will be better. The project is working fine but it doesn't harm to improve it right. So for that I wanted to add pagination for the posts displayed on the home page.

After doing some research I found out that I have to modify both backend and frontend for this. In the backend the process was simple I just had to add 2 lines to the existing query.

```
const posts = await Post.find()
  .populate("author", "id firstName lastName email profile_pic")
  .populate("liked_by", "id")
  .sort({ created_at: -1 })

  // newly added lines

  .skip((page - 1) * perPage)
  .limit(perPage);
```

skip() will skip the number of results mentioned and limit will limit the query result to the desired number. `page` and `perpPage` values will be provided by frontend but they have default values of 1 and 3 in my case. Additionally I am returning the `currentPage` and `totalPages` along with the `posts`.

Now coming to the frontend of things. There were only few changes required. First was adding buttons for moving forwards and backwards. I used [react-icons](https://react-icons.github.io/react-icons/) library for it which is oh so convenient. I found out about it on a yt tutorial video which just goes to show tutorial hell isn't real😉. Anyways, after that each button was used to increase/decrease `currentPage` state and in `useEffect` this `currentPage` value was included in the dependency array. Thus each time user clicks on a button it will call the `fetchPosts` function with the given `currentPage` value.

It all worked like a charm I thought about having infinite scroll but stuck to the simple things. But implementing that shouldn't be that tough. I will just have to monitor mouse position on y axis and when that value reaches some threshold call the api while showing loading spinner. So, that's that. BDW the site was not building properly in gh-pages. Finally when I checked the logs in action tab found out that I ended a `raw` command with `end raw` instead of `endraw`. Goes on to show you not to blindly copy code. All should be fine now though.
