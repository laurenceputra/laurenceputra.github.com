---
layout: post
title: "Cheap US servers for OpenVPN from Singapore"
date: 2013-04-18 23:51:09 +0800
comments: true
categories: tech
---

Just some background stuff that might be useful in future for myself =P.

[Update 1: DigitalOcean now has VPS in San Fran (<a href="https://www.digitalocean.com/blog_posts/digitalocean-opens-san-francisco-datacenter" target="_blank">Link</a>]  
2 main options, AlienVPS and DigitalOcean

Specs

<table width="100%" border="1" cellspacing="2" cellpadding="2">
  <tr>
    <td valign="top">
    </td>
    
    <td valign="top">
      AlienVPS
    </td>
    
    <td valign="top">
      AlienVPS
    </td>
    
    <td valign="top">
      DigitalOcean (New York)
    </td>
    
    <td valign="top">
      DigitalOcean (San Fran)
    </td>
  </tr>
  
  <tr>
    <td valign="top">
      Ping
    </td>
    
    <td valign="top">
      267ms
    </td>
    
    <td valign="top">
      250ms
    </td>
    
    <td valign="top">
      409ms
    </td>
    
    <td valign="top">
      200ms
    </td>
  </tr>
  
  <tr>
    <td valign="top">
      Download Speed
    </td>
    
    <td valign="top">
      1.28Mbps
    </td>
    
    <td valign="top">
      1.35Mbps
    </td>
    
    <td valign="top">
      1.35Mbps
    </td>
    
    <td valign="top">
      1.35Mbps
    </td>
  </tr>
  
  <tr>
    <td valign="top">
      Upload Speed
    </td>
    
    <td valign="top">
      0.62Mbps
    </td>
    
    <td valign="top">
      0.74Mbps
    </td>
    
    <td valign="top">
      0.34Mbps
    </td>
    
    <td valign="top">
      0.78Mbps
    </td>
  </tr>
  
  <tr>
    <td valign="top">
      Price
    </td>
    
    <td valign="top">
      USD$15/year
    </td>
    
    <td valign="top">
      USD$4 a month
    </td>
    
    <td valign="top">
      USD$5/month
    </td>
    
    <td valign="top">
      USD$5/month
    </td>
  </tr>
</table>

[Note, just figured out my test environment, NUS, actually caps traffic, hence the speeds are all pretty slow]

However, despite <a href="http://alienvps.com/vps-hosting-specials/http://" target="_blank">AlienVPS </a> looking better on network end, they use OpenVZ to virtualise. Result is that you are unable to create you own swap partition, and some OS modules are not available [Not exactly a deal breaker as there are ways to get around it].

<a href="https://www.digitalocean.com/pricing" target="_blank">DigitalOcean </a> use KVM (QEMU) and you can pretty much do most stuff with it, BUT you get only 1 core, and high RTT from SG [That is VERY bad if you are using it for regular web surfing].

Personally I&#8217;ve tried both, and I would say that AlienVPS in terms of performance is way better. However for the cheaper option, you may run into memory issues because the amount of memory is really lacking. Now I have set up the $4/month AlienVPS server with OpenVPN, and streaming videos from Hulu is pretty much smooth. Hulu on DigitalOcean (New York) is decent, but may lag at times. That said, DigitalOcean uses SSD, and if that&#8217;s what you are looking for (DB server and stuff), it could fit the use case of a cheap DB server too.