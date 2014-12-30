---
layout: post
title: "How to Set Up a DWM Status Bar with Conky"
description: ""
category: 
tags: []
---
{% include JB/setup %}

### How to Set Up a DWM Status Bar With Conky

{% highlight console %}
sudo apt-get install conky
{% endhighlight %}

{% highlight console %}
sudo gedit ~/.conkyrc
{% endhighlight %}

{% highlight console %}
out_to_console yes
out_to_x no
background no
update_interval 2
total_run_times 0
use_spacer none

TEXT
$mpd_smart cpu ${cpu cpu1}% / ${cpu cpu2}%  :: mem $memperc% ($mem) :: down ${downspeed eth0}K/s up ${upspeed eth0}K/s :: ${time %a %b %d %H:%M%P}
{% endhighlight %}


{% highlight console %}
(conky | while read LINE; do xsetroot -name "$LINE"; done) &
exec dwm
{% endhighlight %}
