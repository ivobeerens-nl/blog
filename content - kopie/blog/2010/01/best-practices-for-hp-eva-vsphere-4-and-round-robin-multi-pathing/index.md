---
title: "Best practices for HP EVA, vSphere 4 and Round Robin multi-pathing"
date: "2010-01-19T10:47:58.000Z"
categories: 
  - "best-practices"
  - "hp-eva"
  - "multi-pathing"
  - "round-robin"
  - "vsphere"
tags: 
  - "hp-eva"
  - "multi-pathing"
  - "round-robin"
---

 To get your HP EVA storage system  and VMware ESX hosts storage balances you get a better performance. Here are some Best practices.

The VMware vSphere and the HP EVA 4x00, 6x00 and 8x00 series are ALUA compliant. ALUA compliant means in simple words that it is not needed to manually identify preferred I/O paths between VMware ESX hosts and the storage controllers.

When you create a new Vdisk on the HP EVA the LUN is set default set to No Preference. The No Preference policy means the following: 

- Controller ownership is non-deterministic. The unit ownership is alternated between controllers during initial presentation or when controllers are restarted
    
- On controller failover (owning controller fails), the units are owned by the surviving controller
    
- On controller failback (previous owning controller returns), the units remain on the surviving controller. No failback occurs unless explicitly triggered.
    

To get a good distribution between the controllers the following Vdisk policies can be used:

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><p align="left"><strong><span style="color: #000000"><font size="2">&nbsp;</font></span></strong><span style="color: #000000"><font size="2"><strong>Path A-Failover/failback</strong></font></span></p><p><span style="color: #000000"><font size="2">– At presentation, the units are brought online to controller A</font></span></p><p><span style="color: #000000"><font size="2">– On controller failover, the units are owned by the surviving controller (B)</font></span></p><p><span style="color: #000000"><font size="2">– On controller failback, the units are brought online on controller A implicitly.</font></span></p></td><td valign="top" width="200"><p align="left"><span style="color: #000000"><font size="2">&nbsp;</font></span><strong><span style="color: #000000"><font size="2">Path B-Failover/failback</font></span></strong></p><p><span style="color: #000000"><font size="2">– At presentation, the units are brought online to controller B</font></span></p><p><span style="color: #000000"><font size="2">– On controller failover, the units are owned by surviving controller (A)</font></span></p><p><span style="color: #000000"><font size="2">– On controller failback, the units are brought online on controller B implicitly.</font></span></p></td></tr></tbody></table>

On the HP EVA half of the Vdisks are set on path A-Failover/failback and the other half  of the Vdisks are set to B-Failover/failback, so that they alternate between controller A and B. This can be done from the HP EVA command view.  Now the vDisk are distributed between the two controllers we can go to the vSphere configuration. On every vSphere host perform an rescan or reboot.

In VMware vSphere the Most Recently Used (MRU) and Round Robin (RR) multi-pathing policies are ALUA compliant. Round Robin load balancing is now officially supported.  These multi-path policies have the following characteristics:

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><span style="font-size: x-small"><span style="font-size: x-small"><font size="2"><strong><span style="color: #000000">MRU:</span></strong></font><p><span style="color: #000000"><font size="2">– Will give preference to an optimal path to the LUN</font></span></p><p><span style="color: #000000"><font size="2">– When all optimal paths are unavailable, it will use a non-optimal path</font></span></p><p><span style="font-size: small"><span style="font-size: small">&nbsp;</span></span><span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000"><font size="2">– When an optimal path becomes available, it will failover to the optimal</font></span></span></span></p><p><span style="color: #000000"><font size="2">– Although each ESX server may use a different port through the optimal controller to the LUN, only a single controller port is used for LUN access per ESX server</font></span></p><p><font size="2"></font></p><p><font size="2"></font></p></span></span></td><td valign="top" width="200"><p><span style="color: #000000; font-size: x-small"><font size="2">&nbsp;<strong>Round Robin:</strong></font></span></p><p><span style="color: #000000; font-size: x-small"></span><span style="color: #000000; font-size: x-small"><font size="2">– Will queue I/O to LUNs on all ports of the owning controllers in a round robin fashion providing instant bandwidth improvement</font></span></p><p><span style="color: #000000; font-size: x-small"><font size="2">– Will continue queuing I/O in a round robin fashion to optimal controller ports until none are available and will failover to the non-optimal paths</font></span></p><p><span style="color: #000000; font-size: x-small"><font size="2">– Once an optimal path returns it will failback to it</font></span></p><p><span style="color: #000000"><font size="2"><span style="font-size: x-small">– <font size="2">Can be configured to round robin I/O to all controller ports for a LUN by ignoring optimal path preference. (May be suitable for a write intensive environment due to increased controller port bandwidth)</font></span></font></span></p></td></tr></tbody></table>

The fixed multi-path policy is not ALUA compliant and therefore not recommend to use.

In vSphere 4 there is new multi-pathing framework. There are three core components:

\- Native Multi-pathing Plugin (NMP), handles the multi-pathing configuration, communicates with the SATP and PSP to indentify path failure conditions.

\- Storage Array Type Plugin (SATP), handles specific operations such as device discovery, error codes and failover.

\- Path Selection Plugin (PSP), handles the best available path, there are three policies fixed, MRU and Round Robin.

PSP are set per LUN, meaning that it is possible to have some LUNs use MRU and other use Round Robin policy. Best practice from HP is to change to PSP from MRU to Round Robin we use the following command in the Service Console:

esxcli nmp satp setdefaultpsp --satp VMW\_SATP\_ALUA --psp VMW\_PSP\_RR

Another Best practice is to set the IOPS (Default the IOPS value is 1000) with a value of 1 (controls how many IOs are sent down a given path before vSphere starts to use the next path) for every LUN by using the following command:

for i in \`ls /vmfs/devices/disks/ | grep naa.600\` ; 

do esxcli nmp roundrobin setconfig --type "iops" --iops\=1 --device $i ;done

But there is a bug when rebooting the VMware ESX server, the IOPS value reverted to a random value. More information can be found on the [Virtual Geek](http://virtualgeek.typepad.com/virtual_geek/2009/12/vsphere-4-nmp-rr-iooperationslimit-bug-and-workaround.html) blog from Chad Sakac. To check the IOPS values on all LUNs use the following command:

for i in \`ls /vmfs/devices/disks/ | grep naa.600\` ; 

do esxcli nmp roundrobin getconfig --device $i ;done

[![image](images/image4_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2010/01/image4.png)

  
To solve this IOPS bug, edit the /etc/rc.local file on every VMware ESX host and and add the  IOPS=1 command. The rc.local file execute after all init scripts are executed.

[](https://www.ivobeerens.nl/wp-content/uploads/2012/01/clip_image0025.jpg)[![clip_image002[5]](images/clip_image0025_thumb1.jpg "clip_image002[5]")](https://www.ivobeerens.nl/wp-content/uploads/2012/01/clip_image00251.jpg)

After adding the IOPS=1 command restart the VMware ESX host and check the IOPS values when its back online.

[![clip_image002[7]](images/clip_image0027_thumb.jpg "clip_image002[7]")](https://www.ivobeerens.nl/wp-content/uploads/2010/01/clip_image0027.jpg)

Now you can check if the the Round Robin policy is active and the LUNs are spread over the two controllers.

<table border="0" cellspacing="0" cellpadding="2" width="400"><tbody><tr><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2010/01/clip_image002.jpg"><span style="color: #000000"><img style="border-right-width: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px" title="clip_image002" border="0" alt="clip_image002" src="images/clip_image002_thumb.jpg" width="244" height="179"></span></a></td><td valign="top" width="200"><a href="https://www.ivobeerens.nl/wp-content/uploads/2010/01/clip_image0024.jpg"><span style="color: #000000"><img style="border-right-width: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px" title="clip_image002[4]" border="0" alt="clip_image002[4]" src="images/clip_image0024_thumb.jpg" width="244" height="177"></span></a></td></tr></tbody></table>

Here are some great PowerCLI one-liners created by [Luc Dekens](http://lucd.info/). Thanks for creating so quickly these one-liners for me!

<table border="0" cellspacing="0" cellpadding="2" width="645"><tbody><tr><td valign="top" width="643"><span style="color: #000000; font-size: x-small"><font size="2">Set the multi-path policy to Round Robin for all hosts:</font></span><div></div><br><div></div><br><div></div><pre><span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000">|</span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">-LunType</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">disk</span><span style="color: #800000">"</span><span style="color: #000000">|</span><span style="color: #5f9ea0; font-weight: bold">where</span><span style="color: #000000"> {</span><span style="color: #800080">$_</span><span style="color: #000000">.MultipathPolicy –</span><span style="color: #ff0000">ne</span><span style="color: #000000"> </span></pre><div></div><pre><span style="color: #000000"></span><span style="color: #800000">"</span><span style="color: #800000">RoundRobin</span><span style="color: #800000">"</span><span style="color: #000000">}|</span><span style="color: #5f9ea0; font-weight: bold">Set-ScsiLun</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">-MultipathPolicy</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">RoundRobin</span><span style="color: #800000">"</span><span style="color: #000000"> </span></pre><div></div><p><span style="color: #000000"><font face="Arial">Get the multi-path policy for one host:</font></span></p><div></div><pre><span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000"> &lt;ESXname&gt; | </span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Select</span><span style="color: #000000"> CanonicalName, </span><span style="color: #800000">MultiPathPolicy</span></pre><div></div><p style="margin: 0cm 0cm 0pt" class="MsoNormal"><span style="color: #000000">&nbsp;</span><span style="color: #000000"><font face="Arial">Get the multi-path policy for all the hosts:</font></span></p><div></div><p style="margin: 0cm 0cm 0pt" class="MsoNormal"><span style="color: #5f9ea0; font-weight: bold"></span></p><div></div><pre><span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">%</span><span style="color: #000000">{</span><span style="color: #800080">$_</span><span style="color: #000000">.Name; </span><span style="color: #800080">$_</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> | </span><span style="color: #5f9ea0; font-weight: bold">Select</span><span style="color: #000000"> CanonicalName, </span><span style="color: #800000">MultiPathPolicy</span><span style="color: #000000">}</span></pre><div></div></td></tr></tbody></table>

\[ad#banner\]

source: Configuration best practices for HP StorageWorks Enterprise Virtual Array (EVA) family and VMware vSphere 4
