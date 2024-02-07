---
aktt_notify_twitter:
- "no"
author: Ivo Beerens
categories:
- disk
- extend
- VMware
- vSphere
date: "2008-08-08T15:36:29Z"
guid: http://www.ivobeerens.nl/?p=32
id: 32
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- Disk
- extend
- VMDK
- VMware
- vSphere
title: How-to extend the VMDK and the Windows disk
url: /2008/08/08/extend-vmdk-disk-and-the-windows-disk/
---

<span style="color: #000000; font-size: small;">I see a lot of environments where the Virtual Machine (VM) disk space must be extended.</span>

<span style="color: #000000; font-size: small;">Prior ESX 3.5 the way to extend a VDMK was to use the vmkfstools command with the -X parameter from the VMware ESX server console. With the coming of ESX 3.5 it is possible to extend the VMDK file when the VM was shutdown. Now with VMware ESX 3.5 Update 2 it is possible to online (hot) extend the VMDK file.</span>

<span style="color: #000000; font-size: small;">In the Virtual Infrastructure Client (VIC) go to the VM and edit the settings, click on the disk there is a property New Size (figure 1).</span>

[<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb.png)</span>](http://localhost/wp-content/uploads/2008/08/image.png)

<span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 1. The VM disk extend function</span></span>

<span style="color: #000000;"><span style="font-size: small;">The first step is to see if there is enough free space on the LUN (datastore). You can check the disk space (realtime) by using the command <span style="font-family: Calibri;"><span style="font-family: courier new;">vdf -h </span><span style="font-family: verdana;">on the ESX server console or in a SSH session. Keep in mind to have a average of 10% free on the LUN for snapshots and swap files etc. </span></span></span></span>

<span style="color: #000000; font-size: small;">If the disk space on the LUN is okay you can extend the disk. In this example we extend the 16GB disk to 20GB.</span>

[<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb1.png)</span>](http://localhost/wp-content/uploads/2008/08/image1.png)

<span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 2. The VM disk extend function</span></span>

<span style="color: #000000; font-size: small;">When the VMDK is extended the disk space must be added to the Windows volume. In the Windows Disk manager when using VMware ESX 3.5 Update 2, use the “Rescan Disks” function to discover the new added space when you use the hot extend function. The new added space is seen as Unallocated</span>

[<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb2.png)</span>](http://localhost/wp-content/uploads/2008/08/image2.png)

<span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 3. Windows disk manager</span></span>

<span style="color: #000000; font-size: small;">To extend the volume by using diskpart use the following commands:</span>

- <span style="color: #000000;"><span style="font-size: small;">Start – run – type <span style="font-family: Calibri;"><span style="font-family: courier new;">diskpart</span> </span></span></span>
- <span style="color: #000000;"><span style="font-size: small;">type <span style="font-family: Calibri;"><span style="font-family: courier new;">list volume</span> </span></span></span>
- <span style="color: #000000;"><span style="font-size: small;">type <span style="font-family: Calibri;"><span style="font-family: courier new;">select volume 1</span> </span></span></span>
- <span style="color: #000000;"><span style="font-size: small;">type <span style="font-family: Calibri;"><span style="font-family: courier new;">extend</span> </span></span></span><span style="color: #000000; font-size: small;">When trying to extend the C partition with diskpart you got the following message “The volume you have selected may not be extended”</span>[<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb3.png)</span>](http://localhost/wp-content/uploads/2008/08/image3.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 4. Diskpart tool</span></span>
    
    <span style="font-size: small;"><span style="color: #000000;">It is not possible to extend the system- and bootvolume by using the diskpart built-in command (for MS Vista, Windows 7 and Windows 2008 and higher you can extend the volume by using diskpart). For MS Windows XP and MS Windows 2003 there are other options you can use:</span> </span>
- <span style="color: #000000; font-size: small;">Add the system- and bootdisk volume to the other Virtuele Machine (VM) as disk. Start the other VM and use the diskpart command to extend this disk or use an 3e party partition tool.</span>
- <span style="font-size: x-small;"><span style="color: #000000;"><span style="color: #000000; font-size: small;">Use the command line tool from Dell called </span>[<span style="color: #000000; font-size: small;">Extpart</span>](http://support.dell.com/support/downloads/download.aspx?c=us&cs=19&l=en&s=dhs&releaseid=R64398&formatcnt=2&fileid=83929)<span style="color: #000000; font-size: small;">. Usage: expart \[drive\] \[sizetoextend\] </span></span></span><span style="font-size: x-small;"><span style="color: #000000;"><span style="color: #000000; font-size: small;"> </span></span></span>
- <span style="font-size: x-small;"><span style="color: #000000;"><span style="color: #000000;"><span style="font-size: small;">Use the Gparted tool. You can download the ISO file from </span>[<span style="font-size: small;">here</span>](http://gparted.sourceforge.net/)<span style="font-size: small;">. </span></span><span style="font-size: 11pt;"> </span></span></span><span style="font-size: x-small;"><span style="color: #000000;"><span style="font-size: 11pt;"><span style="font-size: small;">When the download completes upload the ISO file to your storage and attach and connect the ISO the to the VM.</span></span></span></span>
- <span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb4.png)</span><span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 5. Connect the ISO file to the VM</span></span>
    
    <span style="color: #000000; font-size: small;">Start the VM, the ISO gets started</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb5.png)</span>](http://localhost/wp-content/uploads/2008/08/image5.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 6. Start the Gparted tool</span></span>
    
    <span style="color: #000000; font-size: small;">– Press Enter</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb6.png)</span>](http://localhost/wp-content/uploads/2008/08/image6.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 7. Keymap choice</span></span>
    
    <span style="color: #000000; font-size: small;">– Press OK</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb7.png)</span>](http://localhost/wp-content/uploads/2008/08/image7.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 8. Keyboard layout</span></span>
    
    <span style="color: #000000; font-size: small;">– Select your keyboard layout</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb8.png)</span>](http://localhost/wp-content/uploads/2008/08/image8.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 10. X-windows graphical warning</span></span>
    
    <span style="color: #000000; font-size: small;">– Press Enter</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb9.png)</span>](http://localhost/wp-content/uploads/2008/08/image9.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 11. GParted Parition tool</span></span>
    
    <span style="color: #000000; font-size: small;">– The partition layout is displayed. Select the disk the extend and press Resize/Move</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb10.png)</span>](http://localhost/wp-content/uploads/2008/08/image10.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 12. Partition resize window</span></span>
    
    <span style="color: #000000; font-size: small;">– Enter the new size or drag the bar the the right and press the Resize/ Move button</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb11.png)</span>](http://localhost/wp-content/uploads/2008/08/image11.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 13. Partition resize</span></span>
    
    <span style="color: #000000; font-size: small;">– Click the Apply button</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb12.png)</span>](http://localhost/wp-content/uploads/2008/08/image12.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 14. Partition resize warning</span></span>
    
    <span style="color: #000000; font-size: small;">– Press Apply</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb13.png)</span>](http://localhost/wp-content/uploads/2008/08/image13.png)<span style="color: #000000; font-size: small;">ur</span>
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 15. Partition resize process</span></span>
    
    <span style="color: #000000; font-size: small;">– If the extending process completes and is successfully, restart the system and disconnect the ISO from the VM and restart the VM.</span>
    
    [<span style="color: #000000; font-size: small;">![image](http://localhost/wp-content/uploads/2008/08/image-thumb14.png)</span>](http://localhost/wp-content/uploads/2008/08/image14.png)
    
    <span style="font-size: xx-small;"><span style="color: #000000; font-size: small;">Figure 16. Windows Disk Manager</span></span>
    
    <span style="color: #000000; font-size: small;">– After the restart open the Windows disk manager and you see the new space is added to the volume.</span>
