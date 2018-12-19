---
layout: post
title: Basic web architecture with Nginx and PHP-FPM
---

![Diagram](http://www.programering.com/images/remote/ZnJvbT1jc2RuJnVybD1jR2NxNVNNeUVETjBFVE00QXpMekFqTXdJVE13SXpMbjFXYWtGMmJzQlhkdk1YWnNsbVp2MDJiajV5YjBOV00xNHljbGRXWXRsMkx2b0RjMFJIYQ.jpg){:class='img-responsive' width='100%'}

### FastCGI is a bianry protocol<sup><sup>(1)</sup></sup>, a variation on the earlier CGI (Common Gateway Interface)
CGI process model: one new process per request, then it comes to limitation:
+ Creation and destruction overhead.
+ Resource resuse techniques (database connection, in-memory caching, etc).

FastCGI uses persistent processes to handle series of requests. These processes are owned by FastCGI server, not web server.

FastCGI advantages over embedded interpreters ([mod_perl](https://en.wikipedia.org/wiki/Mod_perl){:target='_blank'}, [mod_php](https://en.wikipedia.org/wiki/List_of_Apache_modules){:target='_blank'}):
+ This separation allows server and application processes to be restarted independently.
+ It also enables the implementation of per-application/ hosting service security policies.
+ Different types of incoming requests can be distributed to specific FastCGI servers which have been equipped to handle those particular types of requests efficiently.

<sup><sup>(1)</sup></sup> bianry protocol: is a protocol which is intended read by a machine rather than human being.

### [PHP-FPM (FastCGI Process Manager) is an alternative PHP FastCGI implementation **with some more features**](https://php-fpm.org/){:target='_blank'}
