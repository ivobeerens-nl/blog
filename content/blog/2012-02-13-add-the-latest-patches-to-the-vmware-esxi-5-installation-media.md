---
author: Ivo Beerens
categories:
- customization
- ESXi
- image builder
- VMware
date: "2012-02-13T23:17:34Z"
guid: http://www.ivobeerens.nl/?p=1296
id: 1296
ssb_fbshare_counts:
- "0"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "0"
tags:
- customization
- esxi
- image builder
title: Customize the VMware ESXi 5 installation media by adding the latest patches
  using Image Builder
url: /2012/02/13/add-the-latest-patches-to-the-vmware-esxi-5-installation-media/
---

<span style="color: #000000;">When you want to customize the VMware ESXi 5 installation media you need to use Image Builder. Image Builder CLI is a set of PowerCLI cmdlets that you can use to manage vSphere image profiles and VIB (VMware Installation Bundle) packages, such as driver VIBs and update VIBs. You can also use Image Builder cmdlets to export an image profile to an ISO or offline depot ZIP file that you can use to install ESXi with a customized set of updates, patches, and drivers</span>

<span style="color: #000000;">In this blog post are the steps outlined on how-to create a customized VMware ESXi5 ISO with the latest patches. Adding the latest patches can be useful because it contains for example the updated HP Emulex net-be2net driver needed for HP Flex-10 ESXi5 installations.</span>

<span style="color: #000000;">More drivers can be found on the VMware download site:</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb11.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image13.png)

#### <span style="color: #000000;">Prerequirements</span>

<span style="color: #000000;">1. Download and install PowerCLI 5.x. Open PowerCLI and set the remote signing to RemoteSigned by using the following command:</span>

<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**Set-ExecutionPolicy RemoteSigned**</span>

<span style="color: #000000;">2. Create a folder structure like this:</span>

> **<span style="color: #000000;"><drive letter>:\\ImageBuil\\ESXi </span>**

<span style="color: #000000;">3. Download the VMware ESXi Offline bundle from the VMware download website and save the file in **<span style="font-family: 'Courier New'; font-size: small;"><driveletter>:\\ImageBuil\\ESXi</span>** </span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb4.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image4.png)

<span style="color: #000000;">The ESXi offline bundle we use is named **<span style="font-family: 'Courier New'; font-size: small;">ESXi500-201111001.zip</span>** </span>

#### <span style="color: #000000;">Create a customized ESXi5 ISO</span>

**<span style="color: #000000;">1. Add the ESXi offline bundle and latest patches to depots</span>**

<span style="color: #000000;">Add the VMware ESXi offline bundle and the latest patches use the <span style="font-family: 'Courier New'; font-size: small;">**Add-EsxSoftwareDepot**</span> command. First add the offline ESXi depot by using the following command: </span>

<span style="color: #000000;"><span style="font-family: 'Courier New'; font-size: small;">**Add-EsxSoftwareDepot F:\\ImageBuil\\ESXi\\ESXi500-201111001.zip**</span> </span>

<span style="color: #000000;">Return a list of all the VMware Installation Bundle (VIB) objects, use the <span style="font-family: 'Courier New'; font-size: small;">**Get-EsxSoftwarePackage**</span> command. This example list all the software package (VIB) objects sorted on release date:</span>

<span style="color: #000000;"><span style="font-family: 'Courier New'; font-size: small;">**Get-EsxSoftwarePackage | select Name,Version,ReleaseDate | sort ReleaseDate**</span> </span>

<span style="color: #000000;">Add the URL of the patch depot (we use the VMware Update Manager URL) using the following command:</span>

<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**Add-EsxSoftwareDepot -DepotUrl https://hostupdate.vmware.com/software/VUM/PRODUCTION/main/vmw-depot-index.xml**</span>

<span style="color: #000000;">List the VMware Installation Bundle (VIB) objects again and see the new VIBs added:</span>

<span style="color: #000000;"><span style="font-family: 'Courier New'; font-size: small;">**Get-EsxSoftwarePackage | select Name,Version,ReleaseDate | sort ReleaseDate**</span> </span>

| [<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb5.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image5.png) | [<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb6.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image7.png) |
|---|---|
| <span style="color: #000000; font-family: 'Courier New';">**output using:** </span>Add-EsxSoftwareDepot F:\\ImageBuil\\ESXi\\ESXi500-201111001.zip | <span style="font-family: 'Courier New';">**<span style="color: #000000;">output using: </span>**</span><span style="font-size: small;">Add-EsxSoftwareDepot -DepotUrl </span>[<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**https://hostupdate.vmware.com/softw**</span>](https://hostupdate.vmware.com/software/VUM/PRODUCTION/main/vmw-depot-index.xml)   [ <span style="color: #000000; font-family: 'Courier New'; font-size: small;">**are/VUM/PRODUCTION/main/vmw-depot-index.xml**</span>](https://hostupdate.vmware.com/software/VUM/PRODUCTION/main/vmw-depot-index.xml) |

<span style="color: #000000;">**2.** **Clone the existing image profile**</span>

<span style="color: #000000;">Run the Get-EsxImageProfile cmdlet to find the name of the profile that you want to clone.</span>

<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**Get-EsxImageProfile | Select Name,CreationTime,AcceptanceLevel | Sort CreationTime | FT -AutoSize**</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb7.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image8.png)

<span style="color: #000000;">Clone the latest image profile using this command: </span>

<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**New-EsxImageProfile -CloneProfile “ESXi-5.0.0-20111204001-standard” -name “VMware ESXi5 custom” -Vendor “Beerens”**</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb8.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image9.png)

**<span style="color: #000000;">3. Export the image profile to ISO</span>**

<span style="color: #000000; font-size: small;">Export an image profile to an ISO image or a ZIP file of component files and folders. The following command export the image profile to an ISO:</span>

<span style="color: #000000; font-family: 'Courier New'; font-size: small;">**Export-EsxImageProfile -ImageProfile “VMware ESXi5 custom” –ExportToIso -FilePath F:\\ImageBuil\\esxi5custom.iso**</span>

<span style="color: #000000;">And you are ready to boot from the new installation media named <span style="font-family: 'Courier New';"><span style="font-size: small;">**esxi5custom.iso.** </span></span><span style="font-size: small;">Check the following components to see if the customization has the desired result: </span></span>

- <span style="color: #000000; font-size: small;">VMware ESXi 5 Boot Menu</span>
- <span style="color: #000000; font-size: small;">VMware ESXi build</span>
- <span style="color: #000000; font-size: small;">Image Profile name</span>

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb9.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image11.png)

[<span style="color: #000000;">![image](http://localhost/wp-content/uploads/2012/02/image_thumb10.png "image")</span>](http://localhost/wp-content/uploads/2012/02/image12.png)
