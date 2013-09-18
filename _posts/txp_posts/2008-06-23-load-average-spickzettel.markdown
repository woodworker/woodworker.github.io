---
layout: post
title: "Load Average Spickzettel"
date: 2008-06-23 08:16:01
comments: true
categories: Linux
---

Da ich es immer wieder lese aber auch immer wieder vergessen hier nochmal ein Spickzettel an mich betreffen Load Average auf Linux/Unix 

{% highlight bash %}
$ cat /proc/loadavg
0.70 0.64 0.58 2/355 10506
{% endhighlight %}

* 0.70 load, gemittelt auf 1 Minute, alle 5 Sekunden neu
* 0.64 gemittelt auf 5 Minuten
* 0.58 gemittelt auf 15 Minuten
* 2/355: Zwei Tasks (Prozeße) von insgesamt 355 sind "Runnable".
* 10506 war/ist die letzte PID des Systems 

load von 1 bedeutet, daß ein Prozeß Ressourcen haben will, bei Linux zählt dabei das warten auf die Platte dazu.

Links: 

* [Load auf Wikipedia](http://de.wikipedia.org/wiki/Load#Der_Load_Average_auf_Unix-Systemen)
* [Erklärung von /proc/loadavg](http://extern.fli4l.de/fli4l_faqengine/faq.php?display=faq&faqnr=36&catnr=1&prog=1&lang=de&layout=def)
