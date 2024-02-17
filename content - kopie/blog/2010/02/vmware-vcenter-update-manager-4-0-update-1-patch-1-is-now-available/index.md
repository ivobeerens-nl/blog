---
title: "VMware vCenter Update Manager 4.0 Update 1 Patch 1 is now available"
date: "2010-02-27T09:04:49.000Z"
categories: 
  - "vmware-update-manager"
tags: 
  - "vmware-update-manager"
  - "vum"
---

 VMware vCenter Update Manager 4.0 Update 1 Patch 1 is now available. This patch resolves the following issues:

- After upgrading Cisco Nexus 1000V VSM to the latest version, you might not be able to patch the kernel of ESX hosts attached to the vDS (KB 1015717)  
      
    Upgrading Cisco Nexus 1000V VSM to the latest version upgrades the Cisco Virtual Ethernet Module (VEM) on ESX hosts attached to the vDS. Subsequently, from the same vSphere Client instance, you might not be able to use a host patch baseline to apply patches to the ESX vmkernel64 or ESXi firmware of hosts attached to the vDS. Applying patches to ESX vmkernel64 or ESXi firmware requires that you include the compatible Cisco Nexus 1000V VEM patch in the baseline. However, this patch might not be available for selection in the Update Manager New Baseline wizard or in the Update Manager patch repository.  
      
    
- Upgrade of Cisco Nexus 1000V version 4.0(4)SV1(1) to version 4.0(4)SV1(2) with Update Manager might fail for hosts with certain patch levels (KB 1017069)  
      
    If you are using Cisco Nexus 1000V version 4.0(4)SV1(1), and the ESX patch bulletins ESX400-200912401-BG or ESXi400-200912401-BG are installed on the host, you might not be able to upgrade to Cisco Nexus 1000V version 4.0(4)SV1(2).  
      
    
- Scanning of hosts in a cluster and staging of patches to hosts in a cluster might take a long time to finish  
      
    The scanning and staging operations of hosts in a cluster run sequentially. If a cluster contains a lot of hosts, scanning and staging patches might take a long time to be completed. Scanning and staging of hosts in a cluster run concurrently on all of the selected hosts in the cluster.

For details regarding these new fixes, please refer to the [release notes](http://app.connect.vmware.com/e/er.aspx?s=524&lid=9519&elq=58f8dfa8201c4aed83af54b94f51482e).

VMware vCenter Update Manager 4.0 Update 1 Patch 1 is available for [download](http://app.connect.vmware.com/e/er.aspx?s=524&lid=9518&elq=58f8dfa8201c4aed83af54b94f51482e).

VMware vCenter Update Manager 4.0 Update 1 is required for installation of this patch.
