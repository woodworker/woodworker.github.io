---
layout: post
title: "First demo for the partlet system"
date: 2013-02-20 17:51
comments: true
categories: 
---

**Tl;DR**: Today i created the first demo implementation for my [p2ee/partlets][1] project based on silex and if can be found [here][2].

A while ago i started a small [fun project][3] to create a nice little web framework that is strongly inspired by my [daily work][4] and also by a very interesting [facebook talk][5]. 
On my trainride back from FrOSCon together with 2 of my colleagues i started to hack down the first very simple implementation and i was pretty impressed how powerfull so few code can be.

But as is it very often with "hacked down" solutions the code was a bit messy, hard dependencies, everything is connected with everything else. So i started to take this nice litte framework and split it up in nice litte pieces. And in this process this one project split up in to 3 very small librarys that i published under an MIT license.

p2ee/preparables
----------------

The preparables lib is the part that is heavyly inspired by facebook technology and in short word it's a programmatically way to define dependencies.

p2ee/baserequirements
---------------------

As i started to implement this small webframework i added some basic requirements for my building blocks and in the work of striping it into small libs i moved the basic requirements and the coresponding resolver classes

p2ee/partlets
-------------

This is actually a implementation of the preparables, that turns the abstract concept of "programmatically dependency injection" into a base for hmvc-like frsameworks. Based on the partlets it is very easy to build your webapp based on self contained building blocks.



  [1]: https://github.com/P2EE/partlets
  [2]: https://github.com/P2EE/silex-partlet-demo
  [3]: https://github.com/P2EE
  [4]: http://www.researchgate.net/
  [5]: http://www.infoq.com/presentations/Evolution-of-Code-Design-at-Facebook
