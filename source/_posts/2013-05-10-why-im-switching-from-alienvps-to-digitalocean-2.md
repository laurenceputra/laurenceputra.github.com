---
layout: post
title: "Why I’m switching from AlienVPS to DigitalOcean"
date: 2013-05-10 23:51:09 +0800
comments: true
categories: tech
---

So I&#8217;ve been a cloud nomad.

4 (or 3) years ago, I started thinking about hosting my blog, and using that as a motivation to pick up web programming. I bought the cheapest plan over at SingaporeHost.sg. 5GB disk space for SGD$8 a month. In fact, the earliest version of this blog was hosted there. After looking around, due to the fact that I decided I need to learn more than how to do programming in PHP, coupled with the fact that AWS had their 1 year free trial, I jumped over. Little did I know that their instances (micro-instance) had <a href="http://hughht5.blogspot.nl/2012/05/amazon-ec2-micro-instance-and-stolen.html" target="_blank">CPU stolen from them all the time</a>. On top of that, the filesystem IO was starting to cost money, and there were days where I had around 50 cents worth of EBS IO. That was when I realised AWS wasn&#8217;t that good a deal. Then I jumped to <a href="http://www.webfaction.com/signup?affiliate=laurencepf" target="_blank">Webfaction</a> and it was really good. But I missed being root, and so I got another machine at AlienVPS. Was happy with their price points ($15/year, $4/month), and I got one of each VPS. They were using OpenVZ, and while that meant that some stuff required tricks to get around, you could get around it. Really slow customer support, but I reckoned with their price points, I shouldn&#8217;t expect too much.

Then came <a href="https://www.digitalocean.com/?refcode=429c319fffa8" target="_blank">DigitalOcean</a>. $5/month on KVM VPS with SSD for storage. It was the dream VPS service. Oh, and it&#8217;s on Tier 1 Bandwidth as well. And despite their cheap price, their customer service has an RTT of 10 minutes. Tried it on various occasions throughout the day, it has always been 10mins. And they even teach you how to set up VPN on their servers. What more can one ask for?

As of now, I have set up OpenVPN plus a couple of sites over to DigitalOcean, and I&#8217;m really glad I did so. And their new datacenter location in San Fran has an RTT of 200ms to SG, couldn&#8217;t have been happier.