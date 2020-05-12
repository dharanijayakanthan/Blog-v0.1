---
title: How browsers works 
date: "2016-09-01T23:46:37.121Z"
layout: post
draft: false
path: "/posts/browsers-working-internals/"
category: "Browser"
tags:
  - "Browsers"
  - "Browsers Internals"
description: "If you open a browser and type a url say www.google.com, our browser does few steps to get the information to us."
---

###How browsers works 🔐


If you have been asking this question yourself or been asked and you actually don't know how it works, or you have read how it works somewhere and you have forgotten, don't be ashamed - Welcome to the world of learning 📖. This article will help you understand the basics of it and that should be enough of knowing if you are a front end guy. 

If you open a browser and type a url say www.google.com, our browser does few steps to get the information to us.

1. Browser will match the domain with the IP address through DNS.
2. Once the IP is found the browser will send a HTTP request
3. The server will respond back with HTTP response
4. Then the browser starts rendering the html, if the html contains additional objects like (css,js or images) the browser will make more additional request to fetch those.

This is all that happens.


We see on the 2nd step the browser makes a HTTP request. Lets dig little deep into it.

Everyone would be knowing that HTTPS are secure than HTTP. 

But why is that ❓

> HTTP is just a protocol, but when paired with TLS or transport layer security it becomes encrypted. This makes it secured.

When HTTP is used, a series of handshakes takes place.

The initial request is sent to the server for a verification. When the server responds that it is the desired server the client then sends a hello message.

At this point the communication becomes encrypted.

At this point the reader communication can proceed. The initial handshakes steps take place in a matter of milliseconds.

The job of TCP slow start  - is designed to gradually expand the amount of data traversing the wire each round trip. The initial packet size is 16kb and doubles on subsequent round trips until a max size is reached. This can vary, but tends to be around 4MB for most connections.

What are the other reasons to use HTTPS ❓

- SEO optimization 🕸
- HTTPS are mandatory for PWA 📱
- You can unlock modern browser features like service workers and hardware APIs like WebUSB and Bluetooth access 👍

thats it for basic.



