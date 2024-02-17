---
title: "Identify LUN IDs in Windows Server 2012 R2"
date: "2013-12-26T19:32:53.000Z"
categories: 
  - "hyper-v"
  - "windows-server-2012"
tags: 
  - "hyper-v-2"
  - "windows-server-2012"
author: Ivo Beerens
---

- **View the disks**

list disk

- **Select a disk**

select disk _<number>_

[![image](images/image_thumb6.png "image")](images/image6.png)

- **View the LUN ID of the disk**

detail disk

[![image](images/image_thumb7.png "image")](images/image7.png)

I didn’t find a PowerShell command to view the LUN IDs. You can create a PowerShell script that uses Diskpart to view all the disks and the corresponding LUN IDs.



