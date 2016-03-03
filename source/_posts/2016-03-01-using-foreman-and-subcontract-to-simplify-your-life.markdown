---
layout: post
title: "Using Foreman and Subcontract To Simplify Your Life"
date: 2016-03-01 16:49
comments: true
categories: [Foreman, Subcontractor, Gems We Love]
author: Adam Bell
---

When working on a complex application, you may need more than one application or service running at one time. This can be a pain to manage without great tools like the [Foreman](https://github.com/ddollar/foreman) and [Subcontractor](https://github.com/pitluga/subcontractor) gems, because you would have to have all of those apps and services open in different tab in order for your one complex app to function properly.
<!-- more -->

Let’s use a simple example. Say we’re developing on a customer_app that requires three other apps: crude_app, silly_app, encouraging_app, and each of these applications sends and receives data from the customer_app.

In this kind of situation, you might open up multiple tabs and start all of your applications or services - except one - and then spend up to 30 minutes asking “Why isn’t this working?” More often, though, you might start up all the right things, but be irritated by how tedious that is. Even if it’s only three applications, that time adds up.

Fortunately, there is a solution. The Foreman and Subcontractor gems help manage this for you. Foreman allows you to manage multiple processes with a Procfile containing a list of all of the applications and/or services you’d like to start up at the same time. Subcontractor allows you to start that process from different directories and under the gem configuration specified by [RVM](https://rvm.io/) or [RBENV](https://github.com/rbenv/rbenv). There are many ways to [configure your Procfile](https://github.com/pitluga/subcontractor) so you can set-up your application just the way you want it; for this post I’ll focus on basic setup,  a couple of small problems, and what I did to get around them.

Here is what you have to do to get started:

1. Install Foreman and Subcontractor
2. Write a Procfile that describes what services you apps you want to run
3. Type “foreman start" in terminal


**Installing Foreman and Subcontractor:**

Foreman and Subcontractor are meant to be run outside the context ruby-gemset, if you use RVM, or any other version manager of your application. Let’s return to our example client_app, with the folder structure below. You want to make sure you’re installing the gems in the client folder not in the subfolders that contain application code.


**Writing a Procfile:**

Each entry in a Procfile (one entry per application or service) follows the basic format:

```ruby
App_name:subcontract package manager, gemset , directory, termination signal, command, port
```

Our example client_app would have a Procfile that includes info for crude_app, funny_app, and customer_app:

```ruby
crude: subcontract --rvm ruby-2.2.3@crude_app --chdir ./crude_app --signal INT -- rails s -p 3001
funny: subcontract --rvm ruby-2.2.3@funny_app --chdir ./funny_app --signal INT -- rails s -p 3001
customer: subcontract --rvm ruby-2.2.3@customer_app--chdir ./customer_app --signal INT -- rails s -p 3001
```

Let’s go through the crude_app Procfile entry piece by piece.

`crude`                    - abbreviation for crude_app

`subcontract`              - flags the following info to be passed into subcontract

`--rvm`                    - RVM is the package manager

`ruby-2.2.3@crude_app`     - our gemset for this project

`--chdir`                  - flag signifying that you’re changing directories

`./crude_app`              - the directory you’re changing to

`--signal`                 - flag signifying that you’re designating termination signal

`INT`                      - the actual termination signal type

`-- rails s -p 300x`       - this is the command to start the process




**Foreman Start:**
After you’ve written your Procfile, make sure you’re in the directory containing the Procfile, then type  “foreman start” in your terminal. Now you’re up and running.


As great as Foreman and Subcontractor are, there are a couple of downsides. These downsides are small, but can cause some hitches. I’ll go through them now, and share with you the workarounds I use.

** All of the rails development logs for each application are in the same window.**

I use the logs as the main source of information when I’m working, and it would be easy to get logs from  crude_app, silly_app, and encouraging_app mixed up. To get around this I’ll open another tab and tail the log manually so i know what’s coming from what.

** Pry breaks all of the things**

If I’m using pry to debug one of our applications that uses Foreman, I’ll run into trouble. When I reach the point where pry will stop execution of my application, I can’t interact with it in the terminal.

To deal with this, I navigate into the Procfile and comment out the line that starts the specific application I’m debugging, then I start that app manually in another tab.


These are pretty minor problems, and they are the only problems I’ve found working with foreman and subcontractor. Overall, these issues are tiny compared with the time I save - given the choice, I’ll go with Foreman and Subcontractor every time.
