---
title: "VMware Horizon View Agent installation order"
date: "2015-11-11T08:49:05.000Z"
categories: 
  - "horizon"
  - "VMware"
tags: 
  - "horizon-view"
  - "VMware"
author: Ivo Beerens
---

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

 

(**\*1**) The NSX File and Network Introspection drivers are not installed by default.

(**\*2**) In App Volumes 2.9 and later you can install the agent in any order.

(**\*3**) When using NVIDIA GPUs

(**\*4**) Upgrade of VMware Tools does not require uninstall and reinstall of Horizon Agent as of Horizon 7.13 and Horizon 8 2106.



