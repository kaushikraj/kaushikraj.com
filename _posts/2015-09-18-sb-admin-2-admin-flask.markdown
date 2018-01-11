---
layout:     post
title:      "SB-Admin-2 with Flask-Admin"
subtitle:   "Now using Flask-Admin and is way more cooler."
date:       2015-09-18 20:30:00
author:     "Kaushik Raj"
header-img: "img/bg/post-3.jpg"
---
<p>
The new template is an improvement over the <a href="{% post_url 2015-08-27-sb-admin-2-python %}">SB-Admin-2 in Python</a> template.
This template uses <a href="http://flask-admin.readthedocs.org/en/latest/">Flask-Admin</a> and
<a href="https://flask-login.readthedocs.org/en/latest/">Flask-Login</a>. Flask-Admin allows to represent all the pages as an admin index.
Flask-Login helps with authentication.
</p>

<p>
Most of the UI controls have been made into macros (where it make sense). The macros get the data from a stub.
</p>

<p align="center">
    <img class="img-responsive" src="{{ site.baseurl }}/img/sb-admin-2.jpg" alt="SB-Admin-2">
</p>

<h2 class="section-heading">
Installation
</h2>

<p>
Clone the code from <a href="https://github.com/kaushikraj/sb-admin-2-flask-admin">https://github.com/kaushikraj/sb-admin-2-flask-admin</a>
</p>

<pre>
    <code>
    $virtaulenv env
    $source env/bin/activate
    $pip install -r requirements.txt
    </code>
</pre>

<p>
Optional step (to get the latest bower components).
</p>

<pre>
    <code>
    $bower install bower.json
    </code>
</pre>

<h2 class="section-heading">
Executing the sample
</h2>

<pre>
<code>
    $python app.py
</code>
</pre>

<p>
Load the URL (http://localhost:5000/) on browser. Use the credentials "john:doe" or "mary:jane" to login.
</p>
