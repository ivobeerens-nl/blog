---
author: Ivo Beerens
categories:
- ESXi
- Home Lab
- Whitebox
date: "2013-09-20T11:23:23Z"
guid: http://www.ivobeerens.nl/?p=2437
id: 2437
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- esxi
- VMware vSphere
title: Enable the Intel I217-V network card in VMware ESXi
url: /2013/09/20/enable-the-intel-i217-v-network-card-in-vmware-esxi/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

The motherboard of my Haswell whitebox contains an Intel I217-V network card. See my “[Haswell low power whitebox for ESXi and Hyper-V](http://localhost/2013/06/25/haswell-low-power-whitebox-for-esxi-and-hyper-v/)” post for more information. The Intel I217-V network card is not recognized by VMware ESXi 5.x by default. On the VMware community I found a [post](https://communities.vmware.com/thread/454771?start=0&tstart=0) with the Intel I217-V ESXi driver attached. To enable the Intel I217-V network card you have two options:

- Inject the driver in the ESXi ISO using for example the “ESXi-Customizer” tool. See my blogpost “[VMware ESXi 5 whitebox NIC support](http://localhost/?s=ESXi+Customizer)” for more information.
- Install the driver when ESXI is already installed. You need a supported network card to be able to install ESXi!

Here is a quick overview how to install the driver when ESXI is already installed:

- Download the driver
- Upload the VIB to a datastore by using the vSphere Client
- Start the SSH service on the ESXI server and make a SSH connection to the ESXi server
- Put the ESXi server in maintenance mode, command: <span style="font-family: Courier New;">esxcli system maintenanceMode set -e true</span>
- Change the ESXi host acceptance level to Community Supported, command: <span style="font-family: Courier New;">esxcli software acceptance set –level=CommunitySupported</span>
- Install the VIB, command: <span style="font-family: Courier New;">esxcli software vib install -v /vmfs/volumes/datastore1/net-e1000e-2.3.2.x86\_64.vib</span>
- Reboot the system after the following message “Message: The update completed successfully, but the system needs to be reboot“,command: <span style="font-family: Courier New;">reboot </span>
- When the ESXi host is up make a SSH connection and exit maintenance mode. Command: <span style="font-family: Courier New;">esxcli system maintenanceMode set -e false</span>

Check if the Intel I217-V network adapter is visible is the vSphere Client or vSphere Web client

[![image](http://localhost/wp-content/uploads/2013/09/image_thumb1.png "image")](http://localhost/wp-content/uploads/2013/09/image1.png)
