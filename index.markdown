---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
---

<div class="hero">
  <div class="content">
    <h1>Hi, I'm Durlav.</h1>
    <p>Web artisan and chess enthusiastic. I drink and i know things🍺. Welcome to my blog.
    </p>
  </div>
  <div class="hero-image">
    <img src="/assets/images/hero-image.svg" alt="featured project">
  </div>
</div>

<div class="gap"></div>

<div class="section latest-post">
  <div class="content">
    <h1><span>My Latest Posts</span></h1>
    <ul>
      {% assign latestPosts = site.posts %} <!-- first 10 posts logic -->
      {% for post in latestPosts %}
        <li>
          <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
          <p>
            <span style="margin-right: 1em">{{ post.date | date: "%-d %B %Y"}}</span>
            {% for category in post.categories %}
              <span class="button">{{ category }}</span>
            {% endfor %}
          </p>
        </li>
      {% endfor %}
    </ul>
  </div>
</div>
