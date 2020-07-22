---
layout: post
title:  "How to secure your wi-fi network"
author: Iga Kovtun
date: '2020-07-20 19:36:00 +0300'
category: guides
summary: Check-list to prevent wi-fi router attack
thumbnail: /assets/img/posts/router_secure/thumbnail.png
---

## Access to the router page

You have to be able to access the router page. Otherwise that means you can not control your security and change anything listed below. 

You can usually access it via following addresses: [192.168.0.1](http://192.168.0.1/) or [192.168.1.1](http://192.168.0.1/) :

<img src="/assets/img/posts/router_secure/router_page1.png" alt="login form" width="100%">

## Change default password

Do NOT leave default login/password "admin/admin". Otherwise any connected user could change any settings to provide unauthorised connections and attacks. Use strong passwords only. 

<img src="/assets/img/posts/router_secure/router_page2.png" alt="wrong password" width="100%">

## Change SSID

SSID is a network name that broadcasted by wi-fi router. Using a default or common SSID can make it easier for bad guys to crack the WPA2 encryption. The network name is part of the encryption algorithm, and password cracking dictionaries (rainbow tables) include common SSIDs. Thus, a popular SSID makes the hacker’s job easier.

This is how my neighbour's SSID looks like (73% are default):

<img src="/assets/img/posts/router_secure/SSID.png" alt="SSID" width="100%">

On the other hand using default SSID marks you as a non-techie whose a router defence are poor . That makes you a priority target for hacker's attack.

## Don't use WPA or WPA/WPA2 mixed

WPA encryption is [cracked](https://gizmodo.com/wpa-wi-fi-security-gets-cracked-your-network-is-no-lon-5078317). The worst thing is that WPA passphrase hashes are seeded from the SSID name and its length and only protects from attackers who don't have access to the password. Also do not use WPA/WPA2 mixed.

Use WPA2 instead or even WPA3 if it's enabled. 

<img src="/assets/img/posts/router_secure/wpa2.png" alt="WPA encryption" width="100%">

You can look for WPA2 Enterprise support. The downside is that it requires a RADIUS server to handle userIDs and passwords. 

<img src="/assets/img/posts/router_secure/wpa_radius.png" alt="WPA RADIUS server" width="100%">

## Disable WPS (Wi-Fi Protected Setup)

WPS is that what makes user's life easier by connecting network with just 8-digit pin. However it makes hackers attack much easier than your life. WPS has dozen of vulnerabilities and it's just 11000 guesses is needed to crack your network. For some wi-fi router your network can be cracked after the first try with WPS. The worst problem with WPS - to crack it you needn't be an advanced user, there are bunch of tools/applications that can hack WPS pin within an hour! For example, [here](https://fossbytes.com/12-best-wifi-hacking-apps-android/) or [here](https://outpost24.com/blog/wps-cracking-with-reaver).

The best choice is to disable WPS at all:

<img src="/assets/img/posts/router_secure/wps.png" alt="WPS" width="100%">

## Don't use UPnP (Universal Plug and Play)

It was designed for IoT devices to be visible on the internet by poke a hole in the firewall. The general problem is that UPnP doesn't require any sort of authentication from the user.  Hence if UPnP is enabled your router allows any application on your computer pretending to be an IoT device send any data from your computer to a malicious web-site using this protocol.  Unless you consciously use this feature or use UPnP-UP (or a similar technology that provides authentication) the best way to be safe is to disable this protocol.

to be used on a LAN where it lets devices poke a hole in the firewall. It is how IoT devices make themselves visible on the Internet, where many of them get hacked, either due to security flaws or the use of default passwords. UPnP was never meant to be used on the Internet, but some routers mistakenly enabled it there too. UPnP doesn’t require any sort of authentication from the user. Any application running on your computer can ask the router to forward a port over UPnP

<img src="/assets/img/posts/router_secure/upnp.png" alt="UPnP" width="100%">

## Disable Remote Management

It also can be named Remote access, Remote Control, Remote Administration, etc.. 

<img src="/assets/img/posts/router_secure/remote_control1.png" alt="remote access" width="100%">

This allows other people to access and configure your router remotely, hence to make enabled any of the vulnerability mentioned above. Otherwise check that it uses HTTPS (not HTTP), change it's port from default

<img src="/assets/img/posts/router_secure/remote_access3.png" alt="remote access protocol" width="100%">

 and even restrict access by source IP address or source network in case you have a static IP address.

<img src="/assets/img/posts/router_secure/remote_controll2.jpg" alt="remote access source IP" width="100%">

## No Guest Networks

Unless you are pretty sure it's secure. It should require:

- WPA2 or higher encryption
- Wi-Fi guest should not be allowed to access the router's admin interface
- Prevent your guests from accessing private LAN network (TP-LINK calls it "Allow Guests to access my local network". D-Link calls it "Internet access only". TRENDNET also calls it "Internet access only")
- the best practice is to have time limits on users before it's going to expire

## Update firmware

This can help to prevent most of the problems listed above. Encrypt methods and protocols is tended to be cracked and keeping update your router firmware may patch all this holes before you're hacked. Just keep in mind that all the features that are mentioned above, some years ago was secure and now claimed to be deprecated or hacking-prone.

<img src="/assets/img/posts/router_secure/firmware_upgrade.png" alt="firmware upgrade" width="100%">