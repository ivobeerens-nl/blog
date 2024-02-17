---
title: "Display VMware Horizon View Pool information using PowerCLI"
date: "2014-01-22T21:32:53.000Z"
categories: 
  - "power"
  - "powercli"
  - "view"
  - "VMware"
tags: 
  - "horizon"
  - "powercli"
  - "VMware-view"
author: Ivo Beerens
---

Here are some examples to use:

Display all the pools and settings:

get-pool

Display the pools with selected fields in table form:

Get-pool | select DisplayName,Pool\_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize

[![image](images/image_thumb1.png "image")](images/image1.png)

Display the some fields in table form and export the pool information to a a text file:

get-pool | select DisplayName,Pool\_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize | out-file c:\\temp\\pools.txt

The get-pool commands does not export all the settings that can be provided in a VMware View pool.



