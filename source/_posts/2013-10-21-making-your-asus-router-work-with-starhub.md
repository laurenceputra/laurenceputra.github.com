---
layout: post
title: "Making your ASUS router work with Starhub"
date: 2013-10-21 23:51:09 +0800
comments: true
categories: tech
---

So I posted about this before, except it was to use your own router instead of using the crappy gateway that Starhub provides. My router was getting old, despite it still being better than Starhub&#8217;s gateway, it was still rather slow. So I got a ASUS AC66. Turns out, you can make your ASUS router spoof itself as Starhub&#8217;s gateway, and instead of having 3 devices (the ONT, Starhub Gateway, ASUS router), you can reduce it to 2.

Below are the settings that you can use to spoof Starhub&#8217;s gateway.

Internet: VID 1071 PRIO 1 or VID 1078 PRIO 1  
IPTV (LAN 4): VID 1099 PRIO 1  
VoIP (LAN 3): VID 1095 PRIO 1  
Authentication: disable  
Host Name: Serial Number of your gateway  
MAC Address: MAC address of your gateway

*Disclaimer: Not all routers can do this, make sure it can support vlan tagging first