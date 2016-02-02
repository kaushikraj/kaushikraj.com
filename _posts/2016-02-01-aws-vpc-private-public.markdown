---
layout:     post
title:      "AWS - VPC with Public/Private Subnet and NAT instance"
subtitle:   "Outbound traffic from private subnet to internet"
date:       2016-02-01 15:12:00
author:     "Kaushik Raj"
header-img: "img/bg/post-8.jpg"
---

<p>
I recently created a VPC with 2 public and 2 private subnets with a NAT instance and spent considerable time
on getting the internet work from the private subnet.
</p>

<p>
The VPC configuration for my project is looks very similar to the one described <a href="http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Scenario2.html">here</a>.
</p>

<p>
Even after getting all the configuration done (Elastic IP for NAT instance, Security Groups, and Disabling Source/Destination Check), 
the outbound traffic to the internet (from private subnet) didn't work till
I found this blogpost - <a href="https://rbgeek.wordpress.com/2014/04/23/add-a-custom-nat-instance-in-aws-vpc/">https://rbgeek.wordpress.com/2014/04/23/add-a-custom-nat-instance-in-aws-vpc/</a>
</p>

<p>
The command that did the trick was executing the following on the NAT instance
</p>

<pre>
    <code>
iptables -t nat -A POSTROUTING -o eth0 -s 10.100.20.0/24 -j MASQUERADE
    </code>
</pre>