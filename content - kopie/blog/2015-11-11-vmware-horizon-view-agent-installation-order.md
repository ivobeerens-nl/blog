---
author: Ivo Beerens
categories:
- horizon
- VMware
date: "2015-11-11T09:49:05Z"
guid: http://www.ivobeerens.nl/?p=4090
id: 4090
ssb_fbshare_counts:
- "2"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:2;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "2"
tags:
- Horizon View
- VMware
title: VMware Horizon View Agent installation order
url: /2015/11/11/vmware-horizon-view-agent-installation-order/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

When configuring a Windows VDI desktop or RDSH session with Horizon, different software components must be installed such as the VMware Tools and the VMware Horizon View Agent. When using User Environment Manager and App Volumes they require an agent too. All these software components must be installed in the correct order in the master/golden image to prevent problems such as for example a black screen when connecting to a Windows VDI desktop using the PCoIP protocol.

The following order can be used with a clean installation:

1. VMware Tools (**\*1**) (**\*4**)
2. VMware Horizon Agent
3. VMware Horizon Direct-Agent
4. VMware User Environment (DEM) agent
5. VMware App Volumes (Agent) (**\*2**)
6. NVIDIA driver (**\*3**)

Uninstall order:

1. NVIDIA driver and reboot
2. VMware App Volumes agent and reboot
3. VMware DEM agent and reboot
4. VMware Horizon Agent and reboot
5. VMware Tools and reboot

Update VMware tools

Upgrade of VMware Tools does not require uninstall and reinstall of Horizon Agent as of Horizon 7.13 and Horizon 8 2106.

(**\*1**) The NSX File and Network Introspection drivers are not installed by default.

(**\*2**) In App Volumes 2.9 and later you can install the agent in any order.

(**\*3**) When using NVIDIA GPUs

(**\*4**) Upgrade of VMware Tools does not require uninstall and reinstall of Horizon Agent as of Horizon 7.13 and Horizon 8 2106.
