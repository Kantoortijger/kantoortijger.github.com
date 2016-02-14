---
layout: post
title: "How to Set Up a DWM Status Bar with Conky"
description: ""
category: 
tags: []
---
{% include JB/setup %}

I recently moved away from Windows and installed Xubuntu. As I am still reading in on all the stuff has to offer, I will document my experiences.

First, I chose for a tiling window manager. As I would like to improve my effiency and move away from the mouse, I soon figured out this would be the way to go. I like [dmw](http://dwm.suckless.org), as it is simple and elegant.

After the installment, I wanted to show some system info in my status panel (in the place of default's dwm 6.0). This is an easy way to do so.

First, you need conky. 

{% highlight console %}
sudo apt-get install conky
{% endhighlight %}

Create a conky config file. 
{% highlight console %}
sudo gedit ~/.conkyrc
{% endhighlight %}

Fill in the following.

{% highlight console %}
out_to_console yes
out_to_x no
background no
update_interval 2
total_run_times 0
use_spacer none

TEXT
$mpd_smart cpu ${cpu cpu1}% / ${cpu cpu2}%  :: mem $memperc% ($mem) :: 
down ${downspeed eth0}K/s up ${upspeed eth0}K/s :: 
${time %a %b %d %H:%M%P}
{% endhighlight %}

Next, open up your ~/.xsession file to make sure that conky's output is piped to dwm with the 'xsetroot' command.

{% highlight console %}
(conky | while read LINE; do xsetroot -name "$LINE"; done) &
exec dwm
{% endhighlight %}
