GSoC 2017 Summary: Docker and Django project
============================================

Introduction
------------

This summer was really exciting because it was my first Google Summer of
Code! I worked for `Freifunk <https://freifunk.net/en/>`__, a
non-commercial initiative for free wireless networks. I would like to
thank them for the opportunity to expand my programming skills and a
great summer. I am excited that I got around to use Git on a serious
multi-developer project and even create my first pull request. I
developed a strong affection for Docker, which I now use for personal
projects as well. After 5 years of programming in Python I am happy to
add Django to my programming skill set.

Summary
-------

My work was split into two main parts, one was working on nodewatcher, a
mesh networking tool, the other was trying to update a long dead repository
of `Wlan Slovenia <wlan-si.net>`__ webpage. My work can be seen in the
following two pull requests:

-  `Pull request for
   nodewatcher <https://github.com/wlanslovenija/nodewatcher/pull/59>`__
-  `Pull request for
   mainpage <https://github.com/wlanslovenija/mainpage/pull/7>`__

Ip space module
---------------

This was my first task. I had to create a module for nodewatcher which
would draw a map of all the networks, something similar to
`this <https://xkcd.com/195/>`__. The module was needed because some huge networks had no idea,
which ip space was used and which was not, this map would give a better idea of how much space is left,
and how it is structured. I started off slow as I had very little
experience with django, it took me about a week to even find where all
the modules where defined and how to implement a new one. Once I
actually got to program in html/javascript, my work progressed very
quickly, I was basically done with it around mid summer. While working i noticed that the 10.0.0.0/8 network is huge,
compared to the small nodes, you could barely see the nodes, this is why I also added the ability to zoom to top-level nodes,
which adds extra clarity to how the nodes are distributed. The positioning is calculated using the hilbert curve, which is a way to map 1d,
numbers to 2d space. It works great for numbers that are power of 2. The drawing is done using d3.js which is good at handling huge amounts of data,
and displaying it in a svg form, which enabled me to implement zoom with ease.

Problems I had
~~~~~~~~~~~~~~

I spent most of my time of the first task researching and learning... I have
never worked with docker, so it took some time to even boot up the
nodewatcher container, never having worked with django it also took a
rather long time to find out how things are done. Anyone working on
nodewatcher in the future should really know this two fields better then
I did going in.

Future
~~~~~~

I still have a few things to add, a better visual representation will be
a good place to start.

Mainpage
--------

This task on the other hand had a really fast start and it ground to a halt
when I started to work on Django. My task was to revive a project not
touched in years still using virtualenv and old pil library which
hasn't been maintained in 10 years. The wlan-slo webpage is a great starting point for,
anyone trying to starting making meshed wifi nodes, being abandoned for so long, some of the pages
functionality was not operational, this would mean that people who wanted to join the community would,
be deterred from doing so. The webpage is split in two containers, one holding the postgresql database for
the webpage the other having the webpage served using uwsgi for djnago and nginx for static files. Having been in a struggle with docker
in my previous task I was afraid my lack of docker is gonna slow me down
but it was quite the opposite. I managed to create both containers in a
week or so, but having to struggle when it came to django.

Problems I had
~~~~~~~~~~~~~~

My lack of django really showed here, I spent days solving simple
problems of miss-configuration, I wish I had a better understanding of
django when working on this project. The second big problem was the fact
that the project was already finished and I was just updating it,
meaning I had no idea where anything was or how things worked. If I
started from the bottom up I am sure I would have learnt more about
django, but the page was too big to do that in this time frame.

Future
~~~~~~

I grew to love docker, even adapting it to a few of my own projects. When
it comes to docker I am sure I can help, however with my current knowledge of django I don't think
I can contribute to the project. I would really like a professional django developer to take a look at it, I am sure I was
missing something really obvious to him, but not to me.

Finishing thoughts
=================

I really enjoyed the opportunity to join an open source development team, it
inspired me to work on more open-source projects... you never know who
you might end up helping down the road. All in all it was a great summer
and I really enjoyed learning about docker and django.