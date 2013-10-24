---
layout: post
title: "The Advantages of a Custom CSS Framework"
date: 2013-10-24 16:27
comments: true
categories: Learning
author: Adam Hendriksen 
---


Your organization is building a premier app. You are confident in your target audience and the excellence of your design, and yet you know that in a rapidly evolving technology environment change is inevitable. NIRD has extensive experience working with a variety of design styles and front-end frameworks. Regardless of the style or framework you choose, the best practice for developing maintainable front-end code is to modularize your front-end elements. Breaking your front-end code into discrete chunks makes it easier to adapt to new technologies, change designs, and add new functionality over the life of the application.

<!-- more -->

Each project starts with web designers translating business needs and customer knowledge into visually appealing style guides for a website. These guides are then “sliced-up” into style and behavior code by front-end developers to efficiently present the back-end business logic to users via a custom user interface.

Front end frameworks are sometimes used to automate portions of this process. One well-known framework is Twitter Bootstrap, which provides complete css stylesheets and prepackaged javascript behaviors to dramatically reduce or eliminate the design process for prototyping applications. For hackathon projects and minimum viable products, Bootstrap can deliver a professional (if stylistically generic) presentation to end users.

What happens when the style for your new site, based on carefully considered branding decisions, doesn't look or behave like Bootstrap? When a web designer presents a style guide for a site, and did not start with Bootstrap elements, some key disadvantages become apparent:

- Bootstrap is highly interconnected css code. Changes can have far-reaching and unanticipated side effects; change becomes expensive.
- If the design was not specifically created with Bootstrap in mind, those beautiful style features your organization has invested in will need to be shoehorned inefficiently and awkwardly into existing framework components.
- As the design changes or is expanded in the future, Bootstrap will be increasingly resistant to modifications. (This is true of designs that began with Bootstrap in mind as well.)

There are a variety of other front-end frameworks that bring fewer visual design opinions with them, opting instead to provide functionality and behavior tools. These frameworks are more flexible, but your custom design may still lead to conflict with your framework when your design needs violate its underlying assumptions. For example, consider how you want your device to display in a mobile context: should it look the same for a small blackberry screen and a large android screen? A given framework may support this, or it may assume that all phone contexts are roughly the same as an iPhone.

Designers can approach this problem by limiting their stylistic and behavior choices to conform with a front-end framework, or a front-end framework can be selected afterward to minimize conflicts with the design intent (absorbing the additional maintenance costs when changes become necessary). Key considerations for choosing a preexisting front-end are:

- Which design components will be useful for this design?
- How many extra features are included that will have to be rendered inert?
- Does the framework bring enough value to overcome the costs of its use?

NIRD has found that the best practice is usually to avoid the compromise altogether. We create consistently and efficiently coded styles and behavior for each project, with a focus on remaining true to the design. Our approach is inspired by [Roy Tomeij](http://roytomeij.com/), using SASS partials to create modular visual components to maximize reuse. When a new component is needed, it becomes simple to extend an existing module or add a new one. Style and behavior become separate concerns, making changes inexpensive and easily understood.

You are investing in the success of your app today with an awesome and intuitive design. Take advantage of NIRD's front end expertise to invest in your app's future.

