---
layout: post
title: "Lessons learnt from setting up a low memory VPS with CentOS"
date: 2012-12-07 23:51:09 +0800
comments: true
categories: tech
---

So recently I decided to scaled down even further in the cloud (well, <a href="http://www.webfaction.com/?affiliate=laurencepf" target="_blank">webfaction</a> is good but it&#8217;s shared, and many of the cloud services online are just expensive [Azure's cheapest with 1GHz dedicated core and 768MB RAM costs around USD$9 a month, while AWS's <a href="http://gregsramblings.com/2011/02/07/amazon-ec2-micro-instance-cpu-steal/" target="_blank">crappy</a> micro instance throttles my server to a standstill regularly]), and I found <a href="http://alienvps.com" target="_blank">this</a>. Got their $19/year plan, and it comes with 192MB RAM, burstable up to 220MB, with CentOS 64bit.

I got one, and all was well, that was, at least before I ran yum update (note, i tested on ubuntu and they had the same problem, so stop saying it&#8217;s a red-hat issue =P). The second I ran yum update, tons of malloc/not-enough-memory errors started popping out. So, first lesson of the day, disable yum&#8217;s fastest mirror plugin (edit the file /etc/yum/pluginconf.d/fastestmirror.conf and set enabled=0). 

After you do that, if you try updating again, you&#8217;ll run into bigger problems. The installation will crash halfway, and before you know it, you will have 2 version of everything on your machine, and fixing it requires you to remove the stuff one by one. The fix for this is to limit the stack size in the operating system. Set your maximum stack size to the amount of RAM you have (ulimit -s 192), and you will be fine. I put it in my /etc/rc.local file to ensure that the limit was always there when scripts were being run.