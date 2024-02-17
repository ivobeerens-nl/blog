---
title: "Unable to remove the Guest Introspection service"
date: "2016-11-09T11:23:39.000Z"
tags: 
  - "nsx"
  - "VMware"
author: Ivo Beerens
---

[![2016-11-08_15h59_00](images/2016-11-08_15h59_00-300x93.png)](images/2016-11-08_15h59_00.png)

After performing the following steps, I was able to remove the Guest Introspection service :

- Put the ESXi host in maintenance mode
- Drag the ESXi host outside the cluster
- Drag the ESXi host back to the cluster
- Reboot the host
- Exit maintenance mode
- Click on resolve in the Service Deployments section

After performing these steps the Guest Introspection service is removed from the host.



