---
author: Ivo Beerens
categories:
- 3i
- ESX
- VMware
date: "2008-08-07T22:11:24Z"
guid: http://www.ivobeerens.nl/?p=20
tags:
- ESX3i
- VMware
title: Enable SSH for VMware ESX 3i
url: /2008/08/07/enable-ssh-for-vmware-esx-3i/
---

There is a hack to enable SSH for VMware ESX 3i. After reading the [VMTN forum](http://communities.vmware.com/thread/131362). Here is the procedure to enable SSH

– Boot ESXi and wait till the till"loaded

– Press ALT-F1, you see the console screen

– Type <span style="font-family: courier new">unsupported</span> and press ENTER

– Enter the root password

– Enter the following command <span style="font-family: courier new">vi /etc/inetd.conf</span>

– Search for the #SSH row

– Remove the # from the SSH row

– Save the config by entering <span style="font-family: courier new">:wq!</span>

– Type <span style="font-family: courier new">ps | grep inetd</span> on the console

– Send a hangup signal by using the following command <span style="font-family: courier new">kill -s HUP <PID></span>

Open now your favorite SSH client (for example Putty) and SSH to the VMware 3i server.
