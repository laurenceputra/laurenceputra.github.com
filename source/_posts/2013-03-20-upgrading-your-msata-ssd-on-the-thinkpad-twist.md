---
layout: post
title: "Upgrading your mSATA SSD on the Thinkpad Twist"
date: 2013-03-20 23:51:09 +0800
comments: true
categories: tech
---

Got a 128GB mSATA SSD for my Thinkpad, as my cache read percent was consistently under 10%. Writing this post because I could not find any documentation online about replacing your mSATA SSD online.

So, a couple of things you need to know about replacing the mSATA SSD on your Thinkpad Twist

*   The cache partition has a limit of 32GB
*   You still need to set aside space (Size of your RAM + a bit more space[I gave it an extra 256MB]) for Intel Rapid Start Technology(RST) (The thing that makes Windows start up faster and recover from hibernate faster)
*   You can use the remaining space as a SSD

**Steps to replace the mSATA SSD**

1.  Buy a mSATA drive of your choice. Recommended size to make full use of the cache and Intel RST: 64GB, more if you want SSD space as well. I went with the <a href="http://www.adata-group.com/index.php?action=product_feature&#038;cid=3&#038;piid=181" target="_blank">ADATA XPG SX300</a>.
2.  Delete the expresscache software from your computer
3.  Unscrew the 2 screws at the base of the laptop that has the keyboard logo beside it.
4.  Remove the keyboard by following the guide (http://schabby.de/lenovo-thinkpad-keyboard-removal/)[Caution! Do it slowly and don't pull it out too hard]
5.  The mSATA slot is on the top left corner of the motherboard. Unscrew the screw that keeps the mSATA device down, and it will pop up.
6.  Extract the card out of the slot, and put in your new mSATA SSD into the mSATA slot.
7.  Put the hardware back together.
8.  Now the fun part. The installation of the drivers and making things work.
9.  Boot up your machine, and install expresscache available at <a href="http://download.lenovo.com/express/HT074404.html" target="_blank">http://download.lenovo.com/express/HT074404.html</a> and install it. The Win7 and Win8 versions are the same. The installation will create a partition for the cache using whatever remaining space there is on the mSATA SSD up to 32GB. Reboot.
10. To make it support Intel Rapid Start Technology, follow the guide over at <a href="http://download.intel.com/support/motherboards/desktop/sb/rapid_start_technology_user_guide_v11.pdf" target="_blank">http://download.intel.com/support/motherboards/desktop/sb/rapid_start_technology_user_guide_v11.pdf</a>
11. And there you have it, your new mSATA SSD is now operational on your computer. If there&#8217;s extra space, you can create a simple volume using the Disk Management (Windows) software. [Win-x, and select Disk Management]