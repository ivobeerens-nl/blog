---
author: Ivo Beerens
categories:
- Uncategorized
date: "2014-11-17T22:59:58Z"
guid: http://www.ivobeerens.nl/?p=3209
id: 3209
ssb_fbshare_counts:
- "3"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:3;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "3"
title: Microsoft Virtual Machine Converter 3.0 multiple disks bug
url: /2014/11/17/microsoft-virtual-machine-converter-3-0-multiple-disk-bug/
---

<span lang="EN-US" style="color: #333333; font-family: 'Georgia',serif; font-size: 10pt;">When converting a Windows 2008 R2 VM that contains multiple disks (VMDKs), the converting process with Microsoft Virtual Machine Converter (MVMC) 3.0 fails with the following error:</span>

> <span lang="EN-US" style="color: #333333; font-family: 'Georgia',serif; font-size: 10pt;">Microsoft Virtual Machine Converter encountered an error while attempting to convert the virtual machine. Log </span>
> 
> <span lang="EN-US" style="color: #333333; font-family: 'Georgia',serif; font-size: 10pt;">Details: A task may only be disposed if it is in a completion state (RanToCompletion, Faulted or Canceled).</span>

<span lang="EN-US" style="color: #333333; font-family: 'Georgia',serif; font-size: 10pt;">This is a bug that was already available in MVMC version 2.0 and fixed in MVMC 2.1. MVMC 2.1 is hard to find so here is a [link](https://onedrive.live.com/redir?resid=570EBBF7BFDEA790!15622&authkey=!APrHxFQBdUYy0wc&ithint=folder%2czip) to my OneDrive.</span>
