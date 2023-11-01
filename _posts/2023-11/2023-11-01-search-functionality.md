---
layout: post
title: "search functionality"
date: 2023-11-01
categories: jekyll search sitemap
permalink: "/post/search-functionality"
---

Added blog search functionality.

It's that time of year when you feel like changing somethings about your gh-pages site. A few days ago I tried adding posts by categories functionality but wasn't able to do it properly. The thing is currently I don't have ruby installed on my machine and without it every time I want to see the changes the new code made I had to push them to github and check on gh-pages site which at the very least tiresome and unproductive. Although I will say I was able to follow jekyll official site guidelines to get posts by categories. At the end it was about modifying the blog page to incorporate the categories and show them while paginating which seemed to much without local installation.

Alright coming to the topic, I added search functionality this time. I had to do very little digging to find [simple-jekyll-search](https://github.com/christian-fei/Simple-Jekyll-Search) library to search for posts in a jekyll site. Some other options were there like programmable search engine by google but they all seemed a bit much. I wanted a plug and play solution and this library provided just that. I will just go through the basic steps to implement it.

First thing is to create a search.json file and add below mentioned lines there. It will create a json list of all the posts so that they can be searched later.

{% raw %}

```
---
layout: none
---
[
  {% for post in site.posts %}
    {
      "title"    : "{{ post.title | escape }}",
      "category" : "{{ post.category }}",
      "tags"     : "{{ post.tags | join: ', ' }}",
      "url"      : "{{ site.baseurl }}{{ post.url }}",
      "date"     : "{{ post.date }}"
    } {% unless forloop.last %},{% endunless %}
  {% endfor %}
]
```

{% end raw %}

Then add an input element for searching like -

```
<div id="search-demo-container">
  <input type="search" id="search-input" placeholder="Search posts...">
  <ul id="results-container"></ul>
</div>
```

I added these lines in my `default layout` so that in each page search bar will show up. In the same file at the end we can add the simple-jekyll-search library like so-

```
<script src="https://unpkg.com/simple-jekyll-search@latest/dest/simple-jekyll-search.min.js"></script>

<script>
  window.simpleJekyllSearch = new SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '{{ site.baseurl }}/search.json',
    searchResultTemplate: '<li><a href="{url}?query={query}" title="{desc}">{title}</a></li>',
    noResultsText: 'No results found',
    limit: 10,
    fuzzy: false,
    exclude: ['Welcome']
  })
</script>
```

We can also directly download and use the `simple-jekyll-search.min.js` file in our site which I have done. The [github page](https://github.com/christian-fei/Simple-Jekyll-Search) provides all the necessary instructions and customization options so check that out.

So finally I have a new attraction in my site. I will work on adding the posts by categories options too. Now that I think about it, it should really be tags instead of categories. Also while at it I have modified the sitemap of the site using this [site](https://www.xml-sitemaps.com/). I guess more minor changes to the site will follow in coming days like making it responsive and all.
