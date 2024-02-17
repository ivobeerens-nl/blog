---
author: Ivo Beerens
categories:
- VMware Update Manager
date: "2010-02-27T11:04:49Z"
guid: http://www.ivobeerens.nl/?p=518
id: 518
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- VMware Update Manager
- vum
title: VMware vCenter Update Manager 4.0 Update 1 Patch 1 is now available
url: /2010/02/27/vmware-vcenter-update-manager-4-0-update-1-patch-1-is-now-available/
---

|   <font color="#000000">VMware vCenter Update Manager 4.0 Update 1 Patch 1 is now available. </font><span style="color: rgb(43,65,112); font-weight: bold"><font color="#000000">This patch resolves the following issues:</font></span>

- <font color="#000000">After upgrading Cisco Nexus 1000V VSM to the latest version, you might not be able to patch the kernel of ESX hosts attached to the vDS (KB 1015717) Upgrading Cisco Nexus 1000V VSM to the latest version upgrades the Cisco Virtual Ethernet Module (VEM) on ESX hosts attached to the vDS. Subsequently, from the same vSphere Client instance, you might not be able to use a host patch baseline to apply patches to the ESX vmkernel64 or ESXi firmware of hosts attached to the vDS. Applying patches to ESX vmkernel64 or ESXi firmware requires that you include the compatible Cisco Nexus 1000V VEM patch in the baseline. However, this patch might not be available for selection in the Update Manager New Baseline wizard or in the Update Manager patch repository.
    
    </font>
- <font color="#000000">Upgrade of Cisco Nexus 1000V version 4.0(4)SV1(1) to version 4.0(4)SV1(2) with Update Manager might fail for hosts with certain patch levels (KB 1017069) If you are using Cisco Nexus 1000V version 4.0(4)SV1(1), and the ESX patch bulletins ESX400-200912401-BG or ESXi400-200912401-BG are installed on the host, you might not be able to upgrade to Cisco Nexus 1000V version 4.0(4)SV1(2).
    
    </font>
- <font color="#000000">Scanning of hosts in a cluster and staging of patches to hosts in a cluster might take a long time to finish The scanning and staging operations of hosts in a cluster run sequentially. If a cluster contains a lot of hosts, scanning and staging patches might take a long time to be completed. Scanning and staging of hosts in a cluster run concurrently on all of the selected hosts in the cluster.
    
    </font>



<font color="#000000">For details regarding these new fixes, please refer to the [release notes](http://app.connect.vmware.com/e/er.aspx?s=524&lid=9519&elq=58f8dfa8201c4aed83af54b94f51482e)</font><font color="#000000"></font><font color="#000000">.</font>

<font color="#000000">VMware vCenter Update Manager 4.0 Update 1 Patch 1 is available for [download](http://app.connect.vmware.com/e/er.aspx?s=524&lid=9518&elq=58f8dfa8201c4aed83af54b94f51482e)</font><font color="#000000"></font><font color="#000000">.</font>

<font color="#000000">VMware vCenter Update Manager 4.0 Update 1 is required for installation of this patch.</font>
