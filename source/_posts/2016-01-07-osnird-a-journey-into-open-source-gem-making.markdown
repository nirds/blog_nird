---
layout: post
title: "OSNird: A Journey Into Open Source Gem-Making"
date: 2016-01-07 15:16
comments: true
categories: [Open Source, OSNird]
author: Whitney Levis
---

###**Part 1: Introduction to GracePeriod & README-Driven-Development**
---

  OSNird (for Open Source NIRD) is a new program here where NIRDs can spend work time contributing to open source projects. One team (Mike Pence, Adam Bell and myself) is writing a gem to address the imbalance that occurs when we place urgent concerns over important concerns and end up with technical debt. We are excited to take you with us on our learning journey in order to inspire more people to contribute to open source.

###**The Vision:**
---

  We all have those moments. Our feature must be shipped today so we cut corners. It’s hard to keep track of those pieces, especially when our manager now considers our feature done and has moved on to bigger and better features for us to implement. To extend and mix  the metaphor: all those cut corners are essentially swept under the rug. You won’t notice a couple under the rug, but eventually the rug becomes difficult to walk over without pain. Often by the time we are tripping over the technical debt, we have forgotten the story of that corner and how we were planning on fixing it. This is very inefficient. GracePeriod is designed to deal with these concerns. It will help developers hold their managers and themselves accountable to keep track of those corners and stay on top of technical debt. Through GracePeriod, we will be able to record contextual information about our  short cuts and our plans for correcting them so we will have a quick refresher available when the debt comes due.
<!-- more -->

###**The Team:**
---

  The GracePeriod contingent of OSNird is pretty new to open source contribution. Before this project, Mike was the only team member who had developed any gems. Mike is our team’s senior developer and is providing a lot of guidance to the rest of the team. Adam and I are junior developers, excited to be getting our feet wet in open source. We all have very different skills, and we have really been enjoying working together to make a helpful tool.

  We are a decentralized team. NIRD has a flexible work from home policy and has team members from all around the country. So with Mike in Florida, and Adam and me in Washington, this is also great experience in remote collaboration.

###**The Initial Exploration:**
---

  Our first step was to look at other gems that tackle similar problems as GracePeriod or that provide well-implemented gem patterns. Rubocop, cucumber and rspec are all gems that you can run from the command line that give you information about your app. Factory_girl is an excellent implementation of a  flexible file structure. Additionally, contracts.ruby provides a good example for establishing rules that raise various warnings or errors when they are broken.

###**README-Driven-Development:**
---

  In order to get our team on the same page with the application, we first wrote a README of what we wanted to build. As with all agile projects, the actual scope and implementation details will change over time, but creating a unifying document was a great way to get our ideas down and discuss any obvious differences in understanding what this gem is for.

  It was during this process that we came up with the name for the gem. Our first thought was time bomb dsl. While a time bomb is a relatively accurate metaphor for what we are doing, it is an unnecessarily  violent image. After some exploration, we started looking at vocabulary around the concept of debt, since it is technical debt that we are discussing. In the language of debt, a grace period is a period of time where no payment is required but the debt is still present. Grace periods come to an end and then there are notifications that repayments must start. This is our goal for this gem - to notify developers and their managers that the grace extended to pieces of technical debt has come to an end and payment is coming due.

  One of the key parts of our README-driven-development process was defining the user experience. How would grace periods be defined? What would be involved in their implementation? This will continue to be a shifting process. Putting a definition to our initial ideas, however, was a great way to get juniors as well as seniors involved early in the creation process since developing ideas and interfaces does not require deep technical know-how. This ability to pull in folks that don’t have the technical experience with gems increased buy-in and allowed the team to coalesce around a central document that everyone had the opportunity to contribute to.

  We hope that you will follow us on our journey as we learn how to make a really cool gem and contribute to open source. We will keep sharing what we learn on this blog, and you can also tune in to our livestreamed mob programming sessions on Fridays from 8am-10am PST at https://www.livecoding.tv/wmuengineer/ . There's even a live chat if you want to interact with us.

Stay tuned for the next post in this series, which will be about setup, configuration, and starting the gem.
