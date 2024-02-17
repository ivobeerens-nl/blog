---
title: "Slow network throughput between Ubiquiti EdgeRouter VLANs"
date: "2018-06-04T19:32:46.000Z"
categories: 
  - "home-lab"
tags: 
  - "home-lab"
author: Ivo Beerens
---

[![](images/1-300x135.png)](images/1.png)

After some troubleshooting I noticed that the throughput within the VLAN was okay  (120 MB/s on a 1 GbE network). The routing between the VLANs is done by Ubiquiti EdgeRouter Lite. I investigated the Ubiquiti EdgeRouter settings by using SSH and noticed that VLAN forwarding for IPv4 was disabled by using the following command:

\[code language="text"\] ubnt@ubnt:~$ show ubnt offload

IP offload module : loaded IPv4 forwarding: enabled vlan : disabled pppoe : disabled gre : disabled IPv6 forwarding: disabled vlan : disabled pppoe : disabled

IPSec offload module: loaded

Traffic Analysis : export : disabled dpi : disabled version : 1.354 \[/code\]

The following commands enable VLAN forwarding for IPv4 and save the setting:

\[code language="text"\] ubnt@ubnt:~$ configure \[edit\] ubnt@ubnt:# set system offload ipv4 vlan enable \[edit\] ubnt@ubnt: commit \[edit\] ubnt@ubnt:# save Saving configuration to '/config/config.boot' ... Done \[edit\] \[/code\]

[![](images/2-300x118.png)](images/2.png)

This config change can be done without a reboot of the router. After making this change the network throughput was as expected. So make sure to do some tests and check VLAN offloading in the Ubiquiti EdgeRouter (it's default disabled).

[![](images/3-300x146.png)](images/3.png)



