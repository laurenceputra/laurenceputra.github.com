---
layout: post
title: "Setting up OpenVPN on a CentOS server and Windows8"
date: 2013-01-21 23:51:09 +0800
comments: true
categories: tech
---

So I&#8217;m bored of using SSH Tunneling. Plus the fact that when I open too many connections, it sometimes dies. So I decided today morning that I will set up a VPN service that I can use to connect securely to the net that is actually designed for this (plus the fact it made the forwarding global helped too).

So my server is technically a OpenVZ server hosted by <a href="http://alienvps.com/vps-hosting/" target="_blank">Alienlayer</a>, with 512MB RAM and 2 2Ghz cores over in Las Vegas. Expected installation to be a breeze, a couple of yum install commands and I&#8217;d be done. Turned out I was wrong.

The initial setup was easy, following the instructions over <a href="http://www.gaggl.com/2012/06/openvpn-install-on-centos-6-server/" target="_blank">here for CentOS</a> and <a href="http://www.ciscopress.com/articles/article.asp?p=605499&#038;seqNum=7" target="_blank">here for Windows</a>. The problem that stumped me was the part when I couldn&#8217;t update the iptables. Searched the net for hours to no end. Finally, with the help of Olipro on <a href="http://serverfault.com/questions/471007/iptables-returns-me-no-chain-target-match-by-that-name" target="_blank">StackExchange</a>, realised that the problem was that the MASQUERADE module didn&#8217;t exist, and as far as I know, not virtualised yet. So couldn&#8217;t use it.

For people who are intending to set up a VPN server in future, here&#8217;s a <a href="https://gist.github.com/3230440" target="_blank">link</a> that you might find useful.