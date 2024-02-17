---
title: "Cool VMware utilities"
date: "2011-05-20T10:41:27.000Z"
categories: 
  - "tools"
  - "utilities"
  - "vmware"
tags: 
  - "tools"
  - "utilities"
  - "vmware"
---

Here are some cool utilities VMware labs created lately. They are definitely worth a try!

\-[Inventory Snapshot](http://labs.vmware.com/flings/inventorysnapshot). Allows a user to "snapshot" a given vCenter inventory configuration and then reproduce it. The "inventory" includes the Datacenter folders, datacenters, clusters, resource pools, vApps, hierarchy, roles and permissions, configuration settings, and custom fields.

It takes a snapshot of the vCenter inventory and creates some binary files and creates a PowerCLI file called “createinventory.ps1”. This PowerCLI script contains commands to re-create the inventory that you've just archived.

[![image](images/image_thumb2.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/05/image2.png)

Can be used on VMware vCenter 4.0 and above and support VMware DVS

\-[PXE Manager for vCenter](http://labs.vmware.com/flings/pxe-manager). Enables ESXi host state (firmware) management and provisioning. Specifically, it allows:

 Automated provisioning of new ESXi hosts stateless and stateful (no ESX)  
    ESXi host state (firmware) backup, restore, and archiving with retention  
    ESXi builds repository management (stateless and statefull)  
    ESXi Patch management  
    Multi vCenter support  
    Multi network support with agents (Linux CentOS virtual appliance will be available later)  
    Wake on Lan  
    Hosts memtest  
    vCenter plugin  
    Deploy directly to VMware Cloud Director  
    Deploy to Cisco UCS blades

[![image](images/image_thumb3.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/05/image3.png)

\-[Thinapped vSphere Client](http://labs.vmware.com/flings/thinapp-vsphere). Run vSphere client 4.1 in a snap. No install, just download the EXE and double-click. Place the ThinApped vSphere client on any network share and it will automatically stream to any Windows PC with no installation, agents, drivers, or specialized servers required. Carry ThinApped vSphere client and your customization on USB stick and now your vSphere client is available on the GO!

[\-vCenter XVP Manager and Converter](http://labs.vmware.com/flings/xvp). VMware vCenter XVP Manager and Converter provides basic virtualization management capabilities for non-vSphere hypervisor platforms towards enabling centralized visibility and control across heterogeneous virtual infrastructures. It also simplifies and enables easy migrations of virtual machines from non-vSphere virtualization platforms to VMware vSphere.

- Management of the following Microsoft Hyper-V platforms:
    - Microsoft Hyper-V Server 2008
    - Microsoft Windows Server 2008 (64-bit) with Hyper-V role enabled
    - Microsoft Hyper-V Server 2008 R2
    - Microsoft Windows Server 2008 R2 with Hyper-V role enabled
- Familiar vCenter Server graphical user interface for navigating through and managing non-vSphere inventory
- Ease of virtual machine migrations from non-vSphere hosts to vSphere inventory
- Compatible with VMware vCenter Server 4.0 & 4.1
- Scalable up to management of 50 non-vSphere hosts

[![image](images/image_thumb4.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2011/05/image4.png)

Very handy when managing Microsoft Hyper-V hosts with VMware vCenter or do a migration from Microsoft Hyper-V to VMware vSphere.

\-[vCMA.](http://labs.vmware.com/flings/vcma) VMware vCenter Mobile Access (vCMA) is a fully configured and ready to run virtual appliance that is required to manage your datacenter from mobile devices such as smartphones and tablets (iPad). Using either a mobile browser or the native iPad application, administrators can now perform various troubleshooting and remediation activities in their VMware environments from anywhere in the world. 

[\-VMware Auto Deploy.](http://labs.vmware.com/flings/vmware-auto-deploy)  VMware Auto Deploy supports automatic PXE boot and customization of large numbers of ESXi systems. Auto Deploy allows rapid deployment and configuration of a large number of ESXi hosts. After a DHCP server has been set up, Auto Deploy PXE boots machines that are turned on with an ESXi image. Auto Deploy then customizes the ESXi systems using host profiles and other information stored on the managing vCenter Server system. You can set up the environment to use different images and different host profiles for different hosts.

VMware Auto Deploy uses Host Profiles, so it will only works if you have a  VMware Enterprise plus license!
