---
layout: post
title: "How to integrate a WYSIWYG editor in Laravel"
description: ""
category: 
tags: [laravel, wyiwyg, howto]
---
{% include JB/setup %}

## How To Implement a WYSIYG editor into your Laravel app
For one of my Laravel projects, I needed some simple WYSIWYG functionality into my forms. My first guess was that there would be some kind of package available, but I didn't foudn an easy solution I was happy with. After some searching, I found a simple WYSIWYG editor that was quite to my liking, CKeditor (http://ckeditor.com/)

Installation is simple. Move the contents of the downloaded archive to a folder your /public/ directory, for example '/public/ckeditor/. Next, implement the JavaScript file into your layout view (in my case, in my admin layout view). You can do this by making use of the script helper.

{% highlight html %}
{% raw %}
{{ HTML::script('ckeditor/ckeditor.js') }}
{% endraw %}
{% endhighlight %}

Next, assign your textareas to a 'ckeditor' class. You can do this by

{% highlight html %}
{% raw %}
{{ Form::textarea('text', null, array(
    'class' => 'ckeditor'
)) }}
{% endraw %}
{% endhighlight %}

Open your page, and you should be set.

Keep in mind that your databse field must be large enough, as the HTML codes can become quite large. I recommended a text field. 


