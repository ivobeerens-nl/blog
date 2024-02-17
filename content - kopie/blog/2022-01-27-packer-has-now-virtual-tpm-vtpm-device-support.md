---
author: Ivo Beerens
categories:
- packer
date: "2022-01-27T20:45:12Z"
guid: https://www.ivobeerens.nl/?p=8220
id: 8220
ssb_old_counts:
- a:5:{s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:0;s:6:"reddit";i:0;s:6:"tumblr";N;}
ssb_total_counts:
- "0"
tags:
- Packer
- vtpm
- Windows 11
title: Packer has now virtual TPM (vTPM) device support
url: /2022/01/27/packer-has-now-virtual-tpm-vtpm-device-support/
yarpp_meta:
- a:1:{s:27:"yarpp_display_for_this_post";i:1;}
---

In an earlier blogpost called “[Use Packer to install Windows 11 and enable vTPM and VBS](http://localhost/2021/10/22/use-packer-to-install-windows-11-and-enable-vtpm-and-vbs/)” I highlighted a workaround for adding a virtual TPM (vTPM) device to a VM in a VMware vSphere environment. A vTPM device is needed for running Windows 11 (without using registry hacks to bypass the TPM device check).

The latest Packer Plugin for VMware vSphere (V1.0.3) has now support for adding a vTPM device. Default a vTPM device is not added to the VM deployed with Packer. So if you want to create a Windows 11 Golden Image for example you can use Packer with the VMware vSphere plugin with a vTPM device.

Here are the high over steps outlined to add a vTPM device when provisioning a new VM with Packer.

- - Download Packer 1.7.9 or later (https://www.packer.io/downloads).
    - Add the VMware vSphere plugin to the HCL configuration file (https://github.com/hashicorp/packer-plugin-vsphere)

```
<span class="pl-en">packer</span> {
  required_version <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>>= 0.0.1<span class="pl-pds">"</span></span>
  <span class="pl-en">required_plugins</span> {
    vsphere <span class="pl-k">=</span> {
      version <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>>= 0.0.1<span class="pl-pds">"</span></span>
      source  <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">"</span>github.com/hashicorp/vsphere<span class="pl-pds">"</span></span>
    }
  }
}
```

<div>[![](http://localhost/wp-content/uploads/2022/01/1-300x100.jpg)](http://localhost/wp-content/uploads/2022/01/1.jpg)</div>- Add a variable to enable vTPM

```
variable "vm_tpm" {
  type = string
  default = "true"
}
```

- In the vsphere-iso section, add the vTPM configuration parameter that uses the vm\_tpm variable to enable the vTPM device (more options can be found here, [link](https://www.packer.io/plugins/builders/vsphere/vsphere-iso))

```
source "vsphere-iso" "win11basic" {
  vTPM = "${var.vm_tpm}"
}
```

- Perform a packer init command to download the Packer plugin binaries define in the config file 
    - packer init config.pkr.hcl
- Run the packer build command to create the VM 
    - packer build config.pkr.hcl

The VM will be created with a vTPM device.

[![](http://localhost/wp-content/uploads/2022/01/2-300x271.jpg)](http://localhost/wp-content/uploads/2022/01/2.jpg)

With Packer and the VMware vSphere plugin, it is now possible to create a VM with a vTPM device which is needed for deploying Windows 11 VMs. This is a great improvement!
