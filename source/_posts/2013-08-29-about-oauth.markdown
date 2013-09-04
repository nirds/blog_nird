---
layout: post
title: "About OAuth"
date: 2013-08-29 21:35
comments: true
categories: Overview
author: Megan Kiest-McFarland
---

OAuth is an open standard for authentication. It can be used in two different ways.

####Mode 1 - Third party authentication
This is the mode primarily talked about on the internet. The idea is that you authorize one site to get limited data from another site using the OAuth API. For example, a site lets you login with your Facebook or Google credentials instead of setting up an account with them, or a Twitter phone app can get and send tweets from your account. 
<!-- more -->
{% img center /images/signin.png 250 150 Example sign in %}

The API Producer (Facebook, etc.) is responsible for validating the user's credentials internally and then giving the Consumer site a special token that the Producer will treat as an authenticated user with limited access. Each Producer specifies what is available via their OAuth API, so it can be as little as email address, or as much as everything about a user on the site. The Producer can also make the authorization tokens expire after a set period of time for additional security. 
The benefit of using OAuth for authentication depends on what the Consumer site needs. At the most basic level, the Consumer site can use another site's user system instead of maintaining a separate one. This is convenient for the user, who does not have to have additional usernames/passwords, and puts the onus of storing the passwords securely on the other site. If the Consumer site wants to interact with the Producer, then the API gives a clear set of available interactions and enforces that the user permitted the Consumer site to perform such actions. So OAuth lets two sites share private data once the user has granted permission for this sharing.

####Mode 2 - Browser pass through
This mode requires that you have control of both the Producer and Consumer sites/servers. It is for when you have two servers that need to talk to each other, but they are not within the same firewall, so they cannot communicate directly. You can use OAuth signatures and the browser to proxy pass the communication.
For example, say that a site has several ebooks that in turn have photos within them. These photos are stored on a separate server than the ebooks and they are authentication controlled. When a browser (aka user) asks for an ebook, the ebook Consumer wants to be able to send the browser working links to the photos so everything looks good in the browser. Since the Consumer knows an authentication token for the Producer, it signs (part of the OAuth protocol) the url and the Producer will then load the links when the browser goes to load the ebook.
This is valuable because it keeps the Producer's data private except when the authorized site asks for it. It is a preset version of mode 1 enabling the servers to act on the behalf of a possibly anonymous user. In addition, if expiration times are added to the Producer's OAuth filtering, then even the permitted user will have limited access to the data.

####Mode 3(ish) - Hybrid
Some sites let you set a single "admin" OAuth token that can then be used to perform the API calls with specific user information contained within the POST command as needed.


Of note, OAuth has two different versions, 1.0 and 2.0. They are not compatible and have very different intentions. This is relevant, because many people argue that the new version is less secure than 1.0 and should not be used. For an explanation from a creator of OAuth 1.0 on the issues with 2.0 see: http://hueniverse.com/2012/07/oauth-2-0-and-the-road-to-hell/
