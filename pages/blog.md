---
layout: page
title: Blog
background: '/assets/img/bg-post.jpg'
permalink: /blog
---

Welcome to my blog. 

NOTE: This page is being updated. Meanwhile go through some of my posts using below links or the [posts page](/blog/posts).

<hr>

{% for post in site.posts limit : 5 %}

<article class="post-preview">
  {% if post.section == "blog" %}
  <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% else %}
    <h3 class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</h3>
    {% endif %}
  </a>
  <p class="post-meta">Posted by
    {% if post.author %}
    {{ post.author }}
    {% else %}
    {{ site.author }}
    {% endif %}
    on {{ post.date | date: '%B %d, %Y' }} &middot; {% include read_time.html content=post.content %}
  </p>
  {% else %}

  {% endif %}

</article>

<hr>

{% endfor %}

<!-- Pager -->
<div class="clearfix">
  <a class="btn btn-primary float-right" href="{{"/blog/posts" | relative_url }}">View All Posts &rarr;</a>
</div>