---
layout: post
title: Server Side Caching
---

### Important note
Before starting implement caching, we should monitor the system to figure out what are the bottlenecks in current system.

There are many reason of the bottlenecks
* DDoS attack.
* Many real requests, and the server couldn't handle all.
* DB server response too slow.
* ...

If the bottleneck come from the performance of web server, or BD server, we should scale these.

Caching can help in reducing request to server, or hit to database.

But it's only helpful for static information.

In case, the web server response all dynamic information, then caching won't help much.

And caching invalidation is hard, need to be considered carefully.

[Another use of caching is preventing DDoS or DoS attack](https://unixy.net/secure/knowledgebase/35/Block-a-DDoS-or-DoS-attack-with-Varnish---Protection-tips.html){:target='_blank'}

### Server-side Caching
![Diagram](https://www.howson.me/content/images/2016/01/Nginx-demo-for-blog-2.png){:class='img-responsive' width='100%'}

  > -- <cite> [Simply Tom (2016) https://www.howson.me](https://www.howson.me/expanding-varnish-to-server-nodejs){:target='_blank'}</cite>

Setup estimation
* There are a few ways to setup cache server:

   * Load balancing → Varnish servers → Web servers
   * Varnish server → Load balancing → Web servers
   * Load balancing → Varnish servers → Load balancing → Web servers
* Time to setup server: not too much.

* Time to config: depends on strategy, mastering the following topic is also needed "Cache invalidation".

* Cost depends on how many new servers needed to be setup, 0..n
