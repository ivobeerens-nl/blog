---
author: Ivo Beerens
categories:
- certificate
- horizon
- view
- VMware
- windows server 2012
date: "2013-06-19T08:42:00Z"
guid: http://www.ivobeerens.nl/?p=2316
id: 2316
ssb_fbshare_counts:
- "1"
ssb_old_counts:
- a:7:{s:10:"googleplus";i:0;s:7:"twitter";i:0;s:9:"pinterest";i:0;s:7:"fbshare";i:1;s:8:"linkedin";i:0;s:6:"reddit";i:0;s:6:"tumblr";i:0;}
ssb_total_counts:
- "1"
tags:
- certificate
- horizon
- view
- VMware
- windows server 2012
title: Create a signed certificate for VMware View Connection Servers using a Windows
  Server 2012 CA
url: /2013/06/19/create-a-signed-certificate-for-vmware-view-connection-servers-using-a-windows-server-2012-ca/
wpgplus_message:
- ""
wpgplus_publish:
- "yes"
---

For VMware Horizon View it is recommends that you configure your VMware View Horizon Servers with a signed SSL certificate. Default when you install a VMware View Horizon servers, a certificate is generated that is not signed by a CA. Because it is not signed by a CA It is possible to to intercept traffic. So it is highly recommend to replace the default certificate with a signed certificate after the installation.

In the VMware View Horizon Administrator dashboard you can see that the Connection Server does not have a valid signed certificate.

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb3.png "image")](http://localhost/wp-content/uploads/2013/06/image3.png)

The following steps explains how-to create a signed certificate and replace the self-signed certificate on the VMware View Horizon Connection Server(s). As CA is a Windows Server 2012 Enterprise Certificate Authority used. The installation of this CA is not part of the steps! The VMware View Horizon Connection Server(s) are installed on Windows Server 2008 R2.

#### <font style="font-weight: bold">Steps on the Windows Server 2012 Certification Authority</font>

- Open the **Certification Authority** program in the tools section in Server Manager from the Windows Server 2012 server
- Expand the server name and right click on Certificate Template and choose **Manage**

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb4.png "image")](http://localhost/wp-content/uploads/2013/06/image4.png)

- Select the **Web Server Template** and choose **Duplicate Template**
- Leave all the fields defaults except the following:
- In General change the **Template** **display name**, **Template name** and **Validity period** and **Renewal period** fields to your needs
- In **Request Handling** mark **Allow private key** to be exported
- In the **Security** add the **computer account** of the View Connection Servers with the **Read, Write and Enroll** permissions checked


| [![image](http://localhost/wp-content/uploads/2013/06/image_thumb5.png "image")](http://localhost/wp-content/uploads/2013/06/image5.png) | [![image](http://localhost/wp-content/uploads/2013/06/image_thumb6.png "image")](http://localhost/wp-content/uploads/2013/06/image6.png) |
|---|---|
| [![image](http://localhost/wp-content/uploads/2013/06/image_thumb7.png "image")](http://localhost/wp-content/uploads/2013/06/image7.png) |  |

- Close the Certificate Templates Console
- In the Certificate Authority choose **New** – **Certificate Template to issue** and select the Certificate Template just created

| [![image](http://localhost/wp-content/uploads/2013/06/image_thumb8.png "image")](http://localhost/wp-content/uploads/2013/06/image8.png) | [![image](http://localhost/wp-content/uploads/2013/06/image_thumb9.png "image")](http://localhost/wp-content/uploads/2013/06/image9.png) |
|---|---|

#### **Steps on the VMware Horizon View Connection Server(s**) 

- Start – Run – MMC
- File – Add Snap-ins – Certificates – Computer Account – Local computer
- Personal – Certificates – All Tasks – Select Request New Certificate

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb10.png "image")](http://localhost/wp-content/uploads/2013/06/image10.png)

- Next
- Choose **Active Directory Enrollment Policy**
- Next
- **Check** the **VMware View** template and select **Properties**

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb11.png "image")](http://localhost/wp-content/uploads/2013/06/image11.png)

- In **subject –** Subject name Type select **Common Name**. Enter the FQDN name of the VMware View Horizon Connection server

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb12.png "image")](http://localhost/wp-content/uploads/2013/06/image12.png)

- In General enter as Friendly name **vdm** in the field

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb13.png "image")](http://localhost/wp-content/uploads/2013/06/image13.png)

– Check in the Private Key – Key Options field if **Make private key exportable** option is checked

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb14.png "image")](http://localhost/wp-content/uploads/2013/06/image14.png)

- OK and press Enroll

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb15.png "image")](http://localhost/wp-content/uploads/2013/06/image15.png)

- Rename the Friendly name of the old self signed certificate to another name as VDM

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb16.png "image")](http://localhost/wp-content/uploads/2013/06/image16.png)

- Restart the **VMware View Connection Server** service.

[![image](http://localhost/wp-content/uploads/2013/06/image_thumb17.png "image")](http://localhost/wp-content/uploads/2013/06/image17.png)

- Wait some time so that the **VMware View Connection Server** can load
- Login the View Administrator portal and within a couple of minutes the dashboard System Health of the Connection Servers should get a green color. The VMware View Connection Servers has now a signed certificate

| [![image](http://localhost/wp-content/uploads/2013/06/image_thumb18.png "image")](http://localhost/wp-content/uploads/2013/06/image18.png) | [![image](http://localhost/wp-content/uploads/2013/06/image_thumb19.png "image")](http://localhost/wp-content/uploads/2013/06/image19.png) |
|---|---|
