---
author: Ivo Beerens
categories:
- best practices
- hp eva
- multi pathing
- round robin
- vSphere
date: "2010-01-19T12:47:58Z"
guid: http://www.ivobeerens.nl/?p=465
id: 465
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- hp eva
- multi pathing
- round robin
title: Best practices for HP EVA, vSphere 4 and Round Robin multi-pathing
url: /2010/01/19/best-practices-for-hp-eva-vsphere-4-and-round-robin-multi-pathing/
---

<span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000; font-size: x-small"> </span></span></span>

<span style="color: #000000"> </span><span style="color: #000000; font-size: x-small"><font size="2">To get your HP EVA storage system and VMware ESX hosts storage balances you get a better performance. Here are some Best practices.</font></span>

<span style="color: #000000; font-size: x-small"><font size="2">The VMware vSphere and the HP EVA 4×00, 6×00 and 8×00 series are ALUA compliant. ALUA compliant means in simple words that it is not needed to manually identify preferred I/O paths between VMware ESX hosts and the storage controllers.</font></span>

<span style="color: #000000"><font size="2"><span style="font-size: x-small"><font size="2">When you create a new Vdisk on the HP EVA the LUN is set default set to No Preference. The No Preference policy means the following:</font></span><span style="font-size: x-small"><span style="font-size: x-small"> </span> </span></font></span>

<span style="color: #000000"><font color="#000000" size="2"></font></span>

<font color="#000000" size="2"></font><span style="font-size: x-small"></span>

- <span style="color: #000000; font-size: x-small"><font size="2"><span style="color: #000000; font-size: x-small"><font size="2">Controller ownership is non-deterministic. The unit ownership is alternated between controllers during initial presentation or when controllers are restarted </font></span>
    
    </font></span>
- <span style="color: #000000; font-size: x-small"><font size="2">On controller failover (owning controller fails), the units are owned by the surviving controller </font></span>
- <span style="color: #000000; font-size: x-small"><font size="2"><span style="color: #000000; font-size: x-small"><font size="2">On controller failback (previous owning controller returns), the units remain on the surviving controller. No failback occurs unless explicitly triggered. </font></span>
    
    </font></span>

<span style="color: #000000"><font size="2">To get a good distribution between the controllers the following Vdisk policies can be used:</font></span>

| **<span style="color: #000000"><font size="2"> </font></span>**<span style="color: #000000"><font size="2">**Path A-Failover/failback** </font></span>  <span style="color: #000000"><font size="2">– At presentation, the units are brought online to controller A </font></span>  <span style="color: #000000"><font size="2">– On controller failover, the units are owned by the surviving controller (B) </font></span>  <span style="color: #000000"><font size="2">– On controller failback, the units are brought online on controller A implicitly. </font></span> | <span style="color: #000000"><font size="2"> </font></span>**<span style="color: #000000"><font size="2">Path B-Failover/failback</font></span>**  <span style="color: #000000"><font size="2">– At presentation, the units are brought online to controller B</font></span>  <span style="color: #000000"><font size="2">– On controller failover, the units are owned by surviving controller (A)</font></span>  <span style="color: #000000"><font size="2">– On controller failback, the units are brought online on controller B implicitly.</font></span> |
|---|---|

<span style="color: #000000"><font size="3"><span style="font-size: x-small"><span lang="EN-US" style="line-height: 115%; font-family: "Arial","sans-serif"; color: black; font-size: 10pt; mso-fareast-font-family: calibri; mso-ansi-language: en-us; mso-fareast-language: en-us; mso-bidi-language: ar-sa; mso-fareast-theme-font: minor-latin">On the HP EVA half of the Vdisks are set on path A-Failover/failback and the other half of the Vdisks are set to B-Failover/failback, so that they alternate between controller A and B. This can be done from the HP EVA command view. Now the vDisk are distributed between the two controllers we can go to the vSphere configuration. On every vSphere host perform an rescan or reboot.</span></span></font></span>

<span style="color: #000000; font-size: x-small"><font size="2">In VMware vSphere the Most Recently Used (MRU) and Round Robin (RR) multi-pathing policies are ALUA compliant. Round Robin load balancing is now officially supported. These multi-path policies have the following characteristics:</font></span>

| <span style="font-size: x-small"><span style="font-size: x-small"><font size="2">**<span style="color: #000000">MRU:</span>** </font><span style="color: #000000"><font size="2">– Will give preference to an optimal path to the LUN </font></span>  <span style="color: #000000"><font size="2">– When all optimal paths are unavailable, it will use a non-optimal path </font></span>  <span style="font-size: small"><span style="font-size: small"> </span></span><span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000"><font size="2">– When an optimal path becomes available, it will failover to the optimal </font></span></span></span>  <span style="color: #000000"><font size="2">– Although each ESX server may use a different port through the optimal controller to the LUN, only a single controller port is used for LUN access per ESX server</font></span>  <font size="2"></font>  <font size="2"></font>  </span></span> | <span style="color: #000000; font-size: x-small"><font size="2"> **Round Robin:**</font></span>  <span style="color: #000000; font-size: x-small"></span><span style="color: #000000; font-size: x-small"><font size="2">– Will queue I/O to LUNs on all ports of the owning controllers in a round robin fashion providing instant bandwidth improvement </font></span>  <span style="color: #000000; font-size: x-small"><font size="2">– Will continue queuing I/O in a round robin fashion to optimal controller ports until none are available and will failover to the non-optimal paths </font></span>  <span style="color: #000000; font-size: x-small"><font size="2">– Once an optimal path returns it will failback to it </font></span>  <span style="color: #000000"><font size="2"><span style="font-size: x-small">– <font size="2">Can be configured to round robin I/O to all controller ports for a LUN by ignoring optimal path preference. (May be suitable for a write intensive environment due to increased controller port bandwidth)</font></span> </font></span> |
|---|---|

<span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000; font-size: x-small"><font size="2">The fixed multi-path policy is not ALUA compliant and therefore not recommend to use.</font></span></span></span>

<span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000; font-size: x-small"><font size="2">In vSphere 4 there is new multi-pathing framework. There are three core components:</font></span></span></span>

<span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000; font-size: x-small"><font size="2">– Native Multi-pathing Plugin (NMP), handles the multi-pathing configuration, communicates with the SATP and PSP to indentify path failure conditions.</font></span></span></span>

<span style="font-size: x-small"><span style="font-size: x-small"><span style="color: #000000; font-size: x-small"><font size="2">– Storage Array Type Plugin (SATP), handles specific operations such as device discovery, error codes and failover.</font></span></span></span>

<span style="color: #000000; font-size: x-small"><font size="2">– Path Selection Plugin (PSP), handles the best available path, there are three policies fixed, MRU and Round Robin.</font></span>

<span style="color: #000000; font-size: x-small"><font size="2">PSP are set per LUN, meaning that it is possible to have some LUNs use MRU and other use Round Robin policy. Best practice from HP is to change to PSP from MRU to Round Robin we use the following command in the Service Console:</font></span>

```
<span style="color: #000000">esxcli nmp satp setdefaultpsp --satp VMW_SATP_ALUA --psp VMW_PSP_RR</span>
```

<span style="font-family: "Courier New"; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial; color: #000000">Another Best practice is to set the IOPS (<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial">Default the IOPS value is 1000)</span></span> with a value of 1 (controls how many IOs are sent down a given path before vSphere starts to use the next path) for every LUN by using the following command: </span></span>

<span style="font-family: "Courier New"; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"></span>

```
<span style="color: #0000ff">for</span><span style="color: #000000"> i </span><span style="color: #0000ff">in</span><span style="color: #000000"> </span><span style="color: #0000ff">`l</span><span style="color: #000000">s /vmfs/devices/disks</span><span style="color: #ff0000">/</span><span style="color: #000000"> | grep naa.600` ; </span>
```

```
<span style="color: #000000"></span><span style="color: #0000ff">do</span><span style="color: #000000"> esxcli nmp roundrobin setconfig --type </span><span style="color: #800000">"</span><span style="color: #800000">iops</span><span style="color: #800000">"</span><span style="color: #000000"> --iops</span><span style="color: #ff0000">=</span><span style="color: #000000">1</span><span style="color: #000000"> --device </span><span style="color: #800080">$i</span><span style="color: #000000"> ;done</span>
```

```
<span style="color: #000000"></span>
```

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial"><span style="color: #000000">But there is a bug when rebooting the VMware ESX server, the IOPS value reverted to a random value. More information can be found on the </span>[<span style="color: #000000">Virtual Geek</span>](http://virtualgeek.typepad.com/virtual_geek/2009/12/vsphere-4-nmp-rr-iooperationslimit-bug-and-workaround.html)<span style="color: #000000"> blog from Chad Sakac. To check the IOPS values on all LUNs use the following command:</span></span></span>

```
<span style="color: #0000ff">for</span><span style="color: #000000"> i </span><span style="color: #0000ff">in</span><span style="color: #000000"> </span><span style="color: #0000ff">`l</span><span style="color: #000000">s /vmfs/devices/disks</span><span style="color: #ff0000">/</span><span style="color: #000000"> | grep naa.600` ; </span>
```

```
<span style="color: #000000"></span><span style="color: #0000ff">do</span><span style="color: #000000"> esxcli nmp roundrobin getconfig --device </span><span style="color: #800080">$i</span><span style="color: #000000"> ;done</span>
```

[<span style="color: #000000">![image](http://localhost/wp-content/uploads/2010/01/image4_thumb.png "image")</span>](http://localhost/wp-content/uploads/2010/01/image4.png)

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial; color: #000000">To solve this IOPS bug, edit the /etc/rc.local file on every VMware ESX host and and add the IOPS=1 command. The rc.local file execute after all init scripts are executed. </span></span>

[<span style="color: #000000"></span>](http://localhost/wp-content/uploads/2012/01/clip_image0025.jpg)[![clip_image002[5]](http://localhost/wp-content/uploads/2010/01/clip_image0025_thumb1.jpg "clip_image002[5]")](http://localhost/wp-content/uploads/2012/01/clip_image00251.jpg)

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial; color: #000000">After adding the IOPS=1 command restart the VMware ESX host and check the IOPS values when its back online. </span></span>

[<span style="color: #000000">![clip_image002[7]](http://localhost/wp-content/uploads/2010/01/clip_image0027_thumb.jpg "clip_image002[7]")</span>](http://localhost/wp-content/uploads/2010/01/clip_image0027.jpg)

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial; color: #000000">Now you can check if the the Round Robin policy is active and the LUNs are spread over the two controllers. </span></span>

| [<span style="color: #000000">![clip_image002](http://localhost/wp-content/uploads/2010/01/clip_image002_thumb.jpg "clip_image002")</span>](http://localhost/wp-content/uploads/2010/01/clip_image002.jpg) | [<span style="color: #000000">![clip_image002[4]](http://localhost/wp-content/uploads/2010/01/clip_image0024_thumb.jpg "clip_image002[4]")</span>](http://localhost/wp-content/uploads/2010/01/clip_image0024.jpg) |
|---|---|

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial"><span style="color: #000000">Here are some great PowerCLI one-liners created by </span>[<span style="color: #000000">Luc Dekens</span>](http://lucd.info/)<span style="color: #000000">. Thanks for creating so quickly these one-liners for me! </span></span></span>

| <span style="color: #000000; font-size: x-small"><font size="2">Set the multi-path policy to Round Robin for all hosts:</font></span> ``` <span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000">\|</span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">-LunType</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">disk</span><span style="color: #800000">"</span><span style="color: #000000">\|</span><span style="color: #5f9ea0; font-weight: bold">where</span><span style="color: #000000"> {</span><span style="color: #800080">$_</span><span style="color: #000000">.MultipathPolicy –</span><span style="color: #ff0000">ne</span><span style="color: #000000"> </span> ```  ``` <span style="color: #000000"></span><span style="color: #800000">"</span><span style="color: #800000">RoundRobin</span><span style="color: #800000">"</span><span style="color: #000000">}\|</span><span style="color: #5f9ea0; font-weight: bold">Set-ScsiLun</span><span style="color: #000000"> </span><span style="font-style: italic; color: #5f9ea0">-MultipathPolicy</span><span style="color: #000000"> </span><span style="color: #800000">"</span><span style="color: #800000">RoundRobin</span><span style="color: #800000">"</span><span style="color: #000000"> </span> ```  <span style="color: #000000"><font face="Arial">Get the multi-path policy for one host:</font></span>  ``` <span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000"> <ESXname> \| </span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> \| </span><span style="color: #5f9ea0; font-weight: bold">Select</span><span style="color: #000000"> CanonicalName, </span><span style="color: #800000">MultiPathPolicy</span> ```  <span style="color: #000000"> </span><span style="color: #000000"><font face="Arial">Get the multi-path policy for all the hosts:</font></span>  <span style="color: #5f9ea0; font-weight: bold"></span>  ``` <span style="color: #5f9ea0; font-weight: bold">Get-VMHost</span><span style="color: #000000"> \| </span><span style="color: #5f9ea0; font-weight: bold">%</span><span style="color: #000000">{</span><span style="color: #800080">$_</span><span style="color: #000000">.Name; </span><span style="color: #800080">$_</span><span style="color: #000000"> \| </span><span style="color: #5f9ea0; font-weight: bold">Get-ScsiLun</span><span style="color: #000000"> \| </span><span style="color: #5f9ea0; font-weight: bold">Select</span><span style="color: #000000"> CanonicalName, </span><span style="color: #800000">MultiPathPolicy</span><span style="color: #000000">}</span> ``` |
|---|

<span style="font-family: 'Courier New'; font-size: 10pt; mso-fareast-font-family: 'Times New Roman'; mso-ansi-language: nl; mso-fareast-language: ar-sa; mso-bidi-language: ar-sa"><span style="font-family: arial"><span style="font-family: courier new"><span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"><span style="color: #000000">\[ad#banner\]</span></span></span></span></span>

<span style="font-family: "Verdana","sans-serif"; font-size: 8pt; mso-bidi-font-family: arial"><span style="color: #000000"> </span></span>

<span style="color: #000000; font-size: xx-small"><font size="2">source: </font><font size="2">Configuration best practices for HP StorageWorks Enterprise Virtual Array (EVA) family and VMware vSphere 4</font> </span>

<span style="color: #000000; font-size: xx-small"> </span>

<span style="color: #000000"> </span>
