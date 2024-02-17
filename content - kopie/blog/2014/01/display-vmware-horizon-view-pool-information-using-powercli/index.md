---
title: "Display VMware Horizon View Pool information using PowerCLI"
date: "2014-01-22T21:32:53.000Z"
categories: 
  - "power"
  - "powercli"
  - "view"
  - "vmware"
tags: 
  - "horizon"
  - "powercli"
  - "vmware-view"
---

For a VMware View Horizon Healthcheck I needed to display all VMware View Pools created and export some settings for documentation. The easiest way to do this is using View PowerCLI on a VMware View Connection server.

Here are some examples to use:

Display all the pools and settings:

get-pool

Display the pools with selected fields in table form:

Get-pool | select DisplayName,Pool\_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize

[![image](images/image_thumb1.png "image")](https://www.ivobeerens.nl/wp-content/uploads/2014/01/image1.png)

Display the some fields in table form and export the pool information to a a text file:

get-pool | select DisplayName,Pool\_ID,Enabled,MinimumCount,MaximumCount,HeadroomCount,Persistence,Pooltype,Protocol | FT -AutoSize | out-file c:\\temp\\pools.txt

The get-pool commands does not export all the settings that can be provided in a VMware View pool.
