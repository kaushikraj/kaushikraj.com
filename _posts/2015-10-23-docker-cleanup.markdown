---
layout:     post
title:      "Cleaning Exited Docker"
subtitle:   "docker ps -a (so many Exited containers)"
date:       2015-10-23 15:12:00
author:     "Kaushik Raj"
header-img: "img/bg/post-4.jpg"
---
<p>
I tend to run docker containers in interactive terminal mode. Over time, this causes tonnes of zombie containers (<code>docker ps -a</code>). 
Removing all those Exited containers is a pain. 
</p>

<p>
The following single line command allows to remove all Exited containers.
</p>

<pre>
    <code>
$docker ps -a | grep Exited | awk '{print $1}' | xargs --no-run-if-empty docker rm
    </code>
</pre>

<p>
If you need to run docker in sudo mode, following is the command for that.
</p>

<pre>
    <code>
$sudo docker ps -a | grep Exited | awk '{print $1}' | xargs --no-run-if-empty sudo docker rm
    </code>
</pre>

<p>
Kill one, Kill All!!
</p>