---
layout:     post
title:      "REST with Flask"
subtitle:   "Reflections on building REST web services with python/Flask"
date:       2015-11-06 14:12:00
author:     "Kaushik Raj"
header-img: "img/bg/post-6.jpg"
---
<p>
I am pretty new to python/non-Microsoft stack. In this post, I reflect on
building a REST web services with python/Flask.
</p>

<h2>python</h2>
<p>
Coming from Microsoft background, I was skeptical about building REST web services with python.
I didn't know python at the start of the project and was the main reason for my apprehensions.
It turned out, learning python wasn't a big issue. Although, some python qualities/limitations kept the
development process pretty interesting/challenging.
</p>
<p>
In my opinion, python is not suitable for *large codebase* because of the following reasons:
<ul>
<li>Python is a scripting language (no compile-time error detection).</li>
<li>Not a true object oriented language.</li>
<li>Complete mess upgrading versions (2.x vs 3.x).</li>
</ul>
</p>
<p>
On the other hand, python has some cool features (I wish .NET had).
<ul>
<li>Virtual environment.</li>
<li>Testing python code is 100 times easier than testing .NET code.</li>
<li>Tuples - .NET has them but they are not as hip.</li>
<li>Deployment with "cp -r"</li>
</ul>
</p>

<h2>Flask</h2>
<p>
There are many frameworks available to build REST web services with python. I settled on Flask because
it seemed the most popular one. For some reason, I was expecting an official framework, just like
ASP.NET is for .NET.
</p>
<p>
Flask is light weight and easy to use framework. It comes with an inbuilt web server. It's embarrasing
that I was stucked with the inbuilt web server for a long time before realizing that the web server is not
suited for production purpose. This situation is not different from ASP.NET/Visual Studio. Although, in case 
of Viusal Studio the development server is rarely used.
</p>

<h2>Routing and Resources</h2>
<p>
Flask comes with base class <code>Resource</code>. It should be use for web methods exposed on a resource.
This <a href="http://blog.miguelgrinberg.com/post/designing-a-restful-api-using-flask-restful">blog post</a> explains how it works.
While it is not required to use <code>Resource</code> base class, I highly recomment it. If the code doesn't use it, route 
maintainence is challenging.
</p>

<h2>virtualenv</h2>
<p>
I absolutely love virtaulenv. Super easy way to isolate dependencies. I highly recommend using virtualenv
during development/testing. It is also a good practice to have "requirements.txt" and "testrequirements.txt" separately.
</p>

<h2>No virtualenv please</h2>
<p>
While virtualenv is great for development, I don't think it should be used for production. There are some known 
<a href="https://news.ycombinator.com/item?id=6859371">issues</a> with virtaulenv.
</p>

<p>
Instead of using virtualenv in the production, it would be better to use Docker. Docker gives the necessary
isolation and easy to deploy mechanism. python already has containers published on Docker <a href="https://hub.docker.com/_/python/">hub</a>.
</p>

<h2>Nginx</h2>
<p>
Ditch the inbuild Flask webserver for nginx. This should be a no-brainer for deploying REST web services in production. My previous 
<a href="{% post_url 2015-11-02-docker-nginx-flask %}">blog</a> talks about this topic.
</p>

<p>
Super thanks to Miguel. His 
<a href="http://blog.miguelgrinberg.com/post/designing-a-restful-api-with-python-and-flask">blog</a> helped a LOT.
There is still so much to learn.
</p>