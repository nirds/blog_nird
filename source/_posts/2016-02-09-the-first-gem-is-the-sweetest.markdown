---
layout: post
title: "The First Gem Is The Sweetest"
date: 2016-02-09 12:01
comments: true
categories: [Open Source, OSNird]
author: Patrick Dent
---

As my colleagues have mentioned in previous posts, we NIRDs have begun an initiative to contribute more to the open source community. As a junior developer who had never contributed to the open source community, this put me on unfamiliar ground. For many, that first step into the unknown is daunting - for me it was terrifying. I mean, I’m mostly self-taught, and as a result, I have a paralyzing fear of everyone discovering that I am a [complete fraud](https://en.wikipedia.org/wiki/Impostor_syndrome). ::Deep breath:: Until now, irrational self-preservation against an imaginary threat has won out over the desire to give back to the community that helped me get to where I am today; but that’s all changed (j/k I’m still scared, but I’m trying to be braver about [failing upwards](http://fortune.com/2014/05/23/the-extraordinary-depressing-power-of-failing-upwards/)).
<!-- more -->

Thankfully, I wasn’t on my own - I was a part of a team! After dipping our toes into the open source pool by making a small contribution to someone else’s project, we decided that we wanted to learn something new - we wanted to build a gem. Since we were new to the process, we wanted to start with something small; conveniently, we had recently written a small amount of Javascript to integrate the handy [will_paginate gem](https://github.com/mislav/will_paginate) into an AngularJS app, so this seemed like as good a point as any from which to proceed.

Since we had never built a gem, we began by researching the process. [Build a Ruby Gem by Brandon Hilkert](http://brandonhilkert.com/books/build-a-ruby-gem/) was thorough coverage of the subject - but actually way more than we needed! See, we wanted to build a gem that fed some Javascript and CSS into the asset pipeline of the apps that would use it - in the larger scheme of things, that’s not too heavy duty. Luckily, there are several [quick](https://gorails.com/episodes/creating-gems-for-frontend-javascript-libraries) and [dirty](http://www.sitepoint.com/create-ruby-gem-jquery-plugin-basics/) [guides](http://brandonhilkert.com/blog/how-to-build-a-rails-engine/) out there on to how to do this!

Since we had already built the feature into a project, it was really straightforward to pull it out into a gem. First, we abstracted the existing code as much as we could and took out any specific references to the app that it lived in. Generic code is reusable code, and what is a gem if not reusable code? Once we had done that, we just followed the guides linked to above on how to turn the code into a gem. Let me lift the main points from [Carlos Becker’s excellent post](http://carlosbecker.com/posts/gemify-your-assets) to demonstrate how straightforward the process is:

1. Create the project skeleton
All this takes is one command in the terminal!

2. Create the vendor/assets folder
In the case of our gem, we actually created the app/assets folder. Why? Because, if you’re including someone else’s javascript in a project, for example, convention dictates that you put it in the vendor/assets folder. It’s not like anything is going to explode if you put javascript you wrote in vendor/assets, but the contents of vendor/assets are understood to be something akin to gems - code by other people that you include in your project. Since we wrote this code, it’s going in our assets folder.

3. Copy the assets to the folders
All we did was move the files from the app we pulled our code from to PRETTY MUCH THE SAME EXACT PLACE (app/assets) in the gem we just made. Magical!

4. Test
Well...it can’t all be easy. This step is conquerable, but was definitely the hardest part of this project - so we’ll cover it in another post.

Once all that was done, we tried out our new gem in our original project by adding it to that project’s gemfile and then bundling. Viola! ng_will_paginate delivered up some nicely paginated angular objects via rails and the will_paginate gem!

There are two morals to this story:

The Ruby on Rails community is a wonderland of handy stuff created by people who are enthusiastic about making useful stuff. This isn’t limited to incredibly niche gems - it includes blog posts about how to make incredibly niche gems!
The bar is easier to surmount than our fears may be telling us - we too, can produce something that is helpful to the community.

I can’t count the number of times stumbling across a casual mention of some small bit of Rails wisdom has helped me in my path to becoming a better developer. If you’ve solved a problem, I can almost guarantee that someone out there will benefit from it if you make it available.


