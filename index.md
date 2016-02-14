---
layout: default
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

About tech, life and more.

 {% for post in site.posts offset: 0 limit: 10  %}
	{{ post.title }} 

 {% endfor %}

## Archive 
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>




