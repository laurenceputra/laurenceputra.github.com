---
layout: post
title: "Getting around Starhub&#8217;s crappy home gateway."
date: 2013-06-16 23:51:09 +0800
comments: true
categories: tech
---

So you had a really awesome router, that had no issue with delivering a working signal into your room, or where ever your computer is. It has been working for a long time.

And one day, Starhub turns up saying that fibre is better, and they have a really awesome home gateway that they will give you for free, and you believed that crap. And you upgrade. And now, your home gateway disconnects every couple of minutes, and you can&#8217;t even achieve the speeds you used to, and the really awesome optical fiber box refuses to let you connect your old router (It&#8217;s the VLAN stuff that they have set up).

Had a chat with Rahul to try to figure out how I should get around this problem, because it&#8217;s really a pain in the ass, and decided to blog about it, simply because of the lack of documentation online.

1.  So if you have an old router previously that was working perfectly, check to see if it&#8217;s using 192.168.0.1 as it&#8217;s IP. If it is, change the home gateway&#8217;s one to 192.168.1.1, with 255.255.0.0 as the subnet, so that the home gateway and your home router doesn&#8217;t conflict.
2.  Next, connect to your home gateway via a ethernet cable, and deactivate the wireless (prevent interference with your router&#8217;s wireless).
3.  Then, connect your router to the home gateway.
4.  Next up, under Status->Lan Clients, check the IP address of your router.
5.  Go to Advanced->DMZ, enable it, select the internet connection for the WAN, and put in the router&#8217;s IP Address as the host.

And you can now connect to your old router and have a functioning wireless network in your house that doesn&#8217;t disconnect regularly.