---
layout: post
title: "Retroactively Setting up a Gem/Engine to Use Rspec"
date: 2016-03-24 12:51
comments: true
categories: [Technical, Gems]
author: Cheri Allen
---

Some of us NIRDs built a gem recently, [ng_will_paginate](https://github.com/nirds/ng_will_paginate), to allow easy use of the fabulous will-paginate gem with an Angular-fronted Rails application. This was the first time we built a gem that uses assets, and it was an excellent learning opportunity. As mentioned in [Patrick’s post](http://blog.nird.us/blog/2016/02/09/the-first-gem-is-the-sweetest/), we traveled a winding path while building this gem. Namely, we extracted the code for it from another project, which meant that we were pulling in fully formed code, and not practicing TDD (please don’t judge us). As a result, we built the gem without the proper testing options and we needed to add them retroactively. This was a complicated thing to research and figure out, but implementation ended up not being too difficult.

<!-- more -->
In this post, I'll walk you through how to implement this yourself:

Since our gem pulls in assets for the client app, it’s considered an engine (you can see this mentioned in many of the guides linked to in Patrick’s post). To test it properly, we'll write code in the dummy app that uses our gem’s functionality, then write javascript specs in the dummy app to test that this functionality is working. In contrast, if we were just writing Ruby code, we’d be able to test with Rspec within the gem’s spec/ directory.

First, we’ll get the dummy app by generating a new plugin project with the same name as our gem, with options to include a dummy app. Then, we can move it into our real project.

 - Navigate outside the gem directory
 - Generate a plugin with the same name as your gem (gem-name in example), with following options: `$rails plugin new gem-name --mountable --dummy-path=spec/dummy --skip-test-unit`
 - Move the generated spec/dummy/ directory to your gem's spec/ directory: `$ mv gem-name/spec/dummy/   path-to/your-actual/gem_name/spec/`
 - Delete that generated plugin - it's worthless now
 - Navigate back to your gem's directory
 - Add the database that the dummy app is configured to use, as a development dependency in your gem's gemspec file (the default is sqlite3)
 - Run `$ bundle install`

Next, we’ll write some tests and run them.

 - In the dummy app, write code that incorporates your gem’s functionality in the way you expect client apps to use it. For us, this meant building a tiny Angular app that had our gem’s service as a dependency, and a single controller that used the service’s methods. This required adding rails, coffee-rails, and angularjs-rails gems to our gemspec file. Because we planned to use [Jasmine](http://jasmine.github.io/) to test, we also added jasmine-rails to the gemspec at this step. Run `$ bundle install` again after all gemspec changes.
 - Next, in the dummy app, write your tests. We used jasmine, and the spec for our service was located at `spec/dummy/spec/javascripts/paginationServiceSpec.js.coffee`.
 - We run our tests the simplest way: by starting a Rails server and visiting http://localhost:3000/specs. Note that this Rails server must be started from within the dummy app, not the gem’s root directory.
 - Now, you can iterate on writing code that more accurately uses the gem’s functionality, changing the gem’s code, and writing better tests, in whatever order you like. Just refresh http://localhost:300/specs to re-run the test suite.


Here are some resources that helped us, and might help you:

 - [How to Write a Gem to Serve Static Files](http://rakeroutes.com/blog/write-a-gem-for-the-rails-asset-pipeline/)
 - [Create a Ruby Gem for a jQuery Plugin](http://www.sitepoint.com/create-ruby-gem-jquery-plugin-basics/)
 - [Getting Started With Engines](http://edgeguides.rubyonrails.org/engines.html)