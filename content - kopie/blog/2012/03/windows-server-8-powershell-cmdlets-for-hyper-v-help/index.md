---
title: "Windows Server 2012 PowerShell Cmdlets for Hyper-V help"
date: "2012-03-07T14:13:45.000Z"
categories: 
  - "hyper-v"
  - "powershell"
  - "windows-8"
tags: 
  - "hyper-v-2"
  - "powershell"
  - "windows-8"
---

In Windows 2008 & Windows2008 R2 there were no official PowerShell Cmdlets available for Hyper-V. This is changed in Windows 2012 and Windows 8. Windows Server 2012 and 8 has 162 or more PowerShell Cmdlets available for Hyper-V. Windows 8 uses PowerShell version 3.

Cmdlets are very powerful, that lets you automate all aspects of Hyper-V.  Here some guidance how-to find the Cmdlets you need.

To view all the Hyper-V PowerShell Cmdlets:

Get-Command -Module Hyper-V

To search for Cmdlets, for example with the name “host” in it: 

Get-Command -Module Hyper-V -Noun \*host\*

[![image](images/image_thumb.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image.png)

To get the Cmdlet syntax:

Get-VMHost -?

 

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image1.png)

Get the Cmdlet syntax and available parameters, details and examples:

get-Help Get-VMHost -Full

[![image](images/image_thumb2.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2012/03/image2.png)

More information over the Hyper-V Cmdlets can be found [here](http://technet.microsoft.com/en-us/library/hh848559.aspx). PowerShell 3.0 is available as Community Technology Preview (CTP) found here.

 

 

\[ad#banner\]
