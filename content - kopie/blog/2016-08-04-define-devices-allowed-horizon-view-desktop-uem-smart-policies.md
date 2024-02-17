---
author: Ivo Beerens
categories:
- Uncategorized
date: "2016-08-04T16:12:00Z"
guid: http://www.ivobeerens.nl/?p=4545
id: 4545
ssb_fbshare_counts:
- "4"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:4;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "4"
tags:
- Horizon View
- VMware
title: Define what devices are allowed in a Horizon View desktop with UEM Smart Policies
url: /2016/08/04/define-devices-allowed-horizon-view-desktop-uem-smart-policies/
---

When designing a new Horizon View environment, one of the design phases is to identify what requirements there are when accessing (redirecting) devices in a Horizon View desktop of published app. In other words what redirection and devices are available and permitted in the VDI desktop or published app such as:

- USB devices
- Clipboard (copy/paste) redirection
- Client Drives Redirection (CDR)
- Printing redirection

For the most environments different requirements are needed when accessing devices from inside or outside the company. Here is an example what redirection/devices are allowed when accessing from inside or outside the company:

| *Endpoint* *location* | **USB** | **Client drive redirection** | **clipboard** | **printing** |
|---|---|---|---|---|
| **inside** | yes | yes | yes | no |
| **outside** | no | no | no | yes |

In User Environment Manager (UEM) 9 there is a new functionality called “Smart Policies”. With Smart Policies you can define what devices are allowed in the VDI desktop based on dynamic conditions such as:

- The endpoint location (inside or outside the company)
- Horizon Tags
- Desktop pool name
- Other View Client variables such as:

[![vars](http://localhost/wp-content/uploads/2016/08/vars-300x251.png)](http://localhost/wp-content/uploads/2016/08/vars.png)

With the endpoint “Client location” condition it is possible to determine when accessing from inside or outside the company. When connecting through the internal Horizon View Connection server the “Client Location” gets the value *Internal*. When connecting through the Horizon View Security Server or Access Point the “Client location” condition get the value *External*. For the different requirements, 2 policies are needed, 1 for internal and 1 for external.

[![Exterbal](http://localhost/wp-content/uploads/2016/08/Exterbal-247x300.png)](http://localhost/wp-content/uploads/2016/08/Exterbal.png) [![Internal](http://localhost/wp-content/uploads/2016/08/Internal-249x300.png)](http://localhost/wp-content/uploads/2016/08/Internal.png)

After defining the policy a condition needs to be set.

- For the internal policy: Property “Client Location” *is equal to* Internal
- For the external policy: Property “Client Location” *is equal to* External

**Example:**

[![4](http://localhost/wp-content/uploads/2016/07/4-300x71.png)](http://localhost/wp-content/uploads/2016/07/4.png)[![3](http://localhost/wp-content/uploads/2016/07/3-221x300.png)](http://localhost/wp-content/uploads/2016/07/3.png)

After defining the conditions both policies are ready to use. In this blog post I showed the strength of using the new Smart Policies option in UEM9. Smart Policies requires UEM9 and Horizon 7 to function.
