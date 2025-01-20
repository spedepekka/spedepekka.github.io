---
layout: page
title: Blog
custom_title: Jarno Tuovinen - Personal Blog
excerpt: Jarno Tuovinen blogs about major events in his life. Most likely it has something to do with Search Engine Optimization or programming.
permalink: /blog/
in_headers: true
---

<div class="home">

  <div id="blog-header-text">
    See <a href="https://rapidprogrammer.com">rapidprogrammer.com</a> for more tech blog posts. This blog contains other topics than just tech topics.
  </div>

  <h2 class="page-heading">Posts</h2>

  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>

</div>
