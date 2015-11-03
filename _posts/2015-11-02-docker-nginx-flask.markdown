---
layout:     post
title:      "Dockerized nginx/Flask App"
subtitle:   "Command line arguments in Docker/Nginx/Flask"
date:       2015-11-02 15:12:00
author:     "Kaushik Raj"
header-img: "img/bg/post-5.jpg"
---
<p>
Flask comes with an in-built webserver. The in-built server is fine for development purpose but
not so much for production. There are multiple options available for using a good webserver. <a href="http://nginx.org">nginx</a>
is a popular choice.
</p>

<p>
When using Flask's in-built server,  command line arguments can be used to initialize certain values.
One can even use `OptionParser` to parse the command line arguments. This is even true when the Flask app
is hosted in Docker container.
</p>

<p>
In case of nginx, where python/Flask is invoked via uwsgi command line arguments is not a viable solution.
</p>

<p>
To workaround the command line argument limitation, one can use environment variables instead. In the following
example, the environment variables are set for the docker container.
</p>

<pre class="code">
$docker run .... -e param1=value1 ....
</pre>

<p>
In the previous case, an environment variable "param1" with "value1" is set for the docker container (at runtime).
To read these environment variables in the flask app, use the following code
</p>

<pre class="code">
using os

param1 = os.environ.get("param1", None)
if param1:
    # param1 was set via environment variable
    # use param1
</pre>

<p>
Checkout a working sample at <a href="https://github.com/kaushikraj/nginx-flask-env">https://github.com/kaushikraj/nginx-flask-env</a>.
In this sample, the output of a method is controlled by environment variable.
</p>