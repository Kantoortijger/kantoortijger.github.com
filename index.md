---
layout: default
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

About tech, life and more.


<hr>

 {% for post in site.posts offset: 0 limit: 1  %}
<div id="post">
  <h1>{{ post.title }}</h1>
  <p class="meta">
    {{ post.date | date_to_long_string }} 
  </p>
  {{ post.content }}
</div>

 {% endfor %}

<hr>

## Archive 
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>




