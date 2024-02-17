---
title: "Patch a vCenter Server High Availability (VCHA) environment"
date: "2021-01-25T20:08:57.000Z"
tags: 
  - "vcenter-server"
  - "VMware"
author: Ivo Beerens
---

When I tried to stage the ISO on the witness node the following error occurred:

> You can not patch a vCenter Server appliance in a vCenter HA cluster. **resolution**: You must remove the vCenter HA configuration, apply patches to vCenter Server appliance, and then reconfigure your vCenter HA deployment.
> 
> [![](images/1-300x63.jpg)](images/1.jpg)

So I removed the vCenter Server HA cluster configuration and patched the single vCenter Server Appliance.

[![](images/2-300x188.jpg)](images/2.jpg)

After the patching of the single VCSA, I redeployed the VCHA cluster again.

**Conclusion**: The vCenter Server HA cluster documentation still has the VCHA 6 update procedure documented that does not work anymore. I will update this blog article if there is more information available.



