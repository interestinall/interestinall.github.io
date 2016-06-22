---
layout: post
title:  "Building a Sinatra Blog"
date:   2016-06-22 17:05:39 +0000
---


Building out a blog platform with sinatra was a rewarding learning experience. In contrast to heavier frameworks like rails, sinatra contains a lot less "magic." This lack of magic is a feature that allows developers the opportunity to see exactly how routes are made, params sent and received and so on. You have to build everything from scratch.

If you decide to do something similar yourself, [pry](https://github.com/pry/pry) is your friend. It makes creating the controller actions a breeze. Here's my advice: 

1. Make the route.
2. Make the form.
3. Put `binding.pry` as the action code in the controller.

If you set up the route and form right, shotgun will pause at `binding.pry` (if not, find out where you made a typo in steps one and two). Once stopped you can fish around in the params and make sure that the correct data is coming through. If it's not, then change the form/route until it is. Doing it this way will save you a lot of time wondering why your controller action doesn't work (hint: janky params). Once you are sending the right params, write your action code. Test it. Ship it. Done.

Since the views weren't going to be very complicated for this project, I decided to try out [HAML](http://haml.info/) for the first time. It was fun to learn a new templating language and I have to say it made form creation, which I typically find annoying, painless. I have more HAML to learn, but the taste I got through this project made me want to go ahead and get good at it. HTML is not difficult, but sometimes I feel like I am writing a novel. And who really loves counting divs to find out what should close where? In contrast, HAML involves a lot less typing and you'll never look for a closing div again.

Check out [Sinatra Blog](https://github.com/interestinall/sinatra-blog) yourself. It's a great starting place for building out a more feature-rich, highly customized, sinatra blog as well as a great blank slate app for improving your css/sass.

