---
layout: post
title: "Retroactively Setting up a Gem/Engine to Use Rspec"
date: 2016-01-18 12:51
comments: true
categories: Technical
author: Cheri Allen
---

We've started building a gem to allow easy use of the fabulous ng-will-paginate gem with an Angular-fronted Rails application. This is the first time we've built a gem that uses assets, and it's been an excellent learning opportunity.

We initally built the gem without the proper testing options (Rspec and a dummy app), so needed to add them retroactively.

To set up your gem to use Rspec:

- change contents of spec/spec_helper.rb to:
  ```ENV["RAILS_ENV"] ||= 'test'

    require File.expand_path("../dummy/config/environment.rb", __FILE__)```
- add dependencies to your gem's gemspec file:
```spec.add_development_dependency "rspec"

    spec.add_development_dependency "rspec-rails"

    spec.add_development_dependency "rails"```
- if you want 'spec' to be the default rake task, change your Rake file to look like this:
``` require 'rspec/core/rake_task'

    require "bundler/gem_tasks"

    RSpec::Core::RakeTask.new(:spec)

    task :default => :spec```
- next, realize you must have a dummy Rails app in your spec/ directory because your gem is a Rails Engine because it includes assets for the client application


To add a spec/dummy directory to an existing gem or Rails engine that you generated without including a dummy app when generating, do the following:

- navigate outside the gem directory
- generate a plugin with the SAME NAME as your gem, with folowing options:
  ```$rails plugin new gem_name  --mountable --dummy-path=spec/dummy --skip-test-unit```
- move the generated spec/dummy/ directory to your gem's spec/ directory:
  ```$ mv gem_name/spec/dummy/ worky/nird/gem_name/spec/```
- delete that generated plugin, it's worthless now
- navigate back to your gem's directory
- add 'sqlite3', or whichever db you've configured dummy app to use, as a development dependency in your gem's gemspec file
- bundle
- run 'rspec spec' or 'rake'
- see tests run without error, weep tears of joy


