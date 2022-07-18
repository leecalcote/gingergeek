---
id: 960
title: Redfish slipstreams IPMI with 1.0 release
date: 2015-08-12T22:55:34+00:00
author: Lee
excerpt: |
  Last week, I was delighted to join in heralding the announcement the release of the Redfish 1.0 specification and highlight Seagate’s support of this emerging systems management API standard.
  
  For those unfamiliar with this newly minted, industry API specification, understand that Redfish is a standard for data center and systems management that delivers improved performance, functionality, scalability and security. Designed to meet the expectations of end users for simple and interoperable management of modern scalable platform hardware, Redfish takes advantage of widely-used technologies to speed implementation and help system administrators be more effective.
layout: post
guid: http://gingergeek.com/?p=960
permalink: /2015/08/redfish-slipstreams-ipmi-with-1-0-release/
articleimg:
  - http://gingergeek.com/wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg
dsq_thread_id:
  - "4744833701"
image: /wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg
categories:
  - redfish
  - systems management
tags:
  - redfish
---
 

[<img class="alignleft size-medium wp-image-969" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg?resize=300%2C211" alt="DMTF Redfish Logo" srcset="https://i2.wp.com/gingergeek.com/wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg?resize=300%2C211 300w, https://i2.wp.com/gingergeek.com/wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg?w=375 375w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/gingergeek.com/wp-content/uploads/2015/08/DMTF-Redfish-Logo.jpg)Last week, I was delighted to join in heralding the [announcement the release](http://www.dmtf.org/news/pr/2015/8/dmtf-helps-enable-multi-vendor-data-center-management-new-redfish-10-standard) of the Redfish 1.0 specification and highlight Seagate’s support of this emerging systems management API standard.

For those unfamiliar with this newly minted, [industry API specification](http://dmtf.org/standards/redfish), understand that Redfish is a standard for data center and systems management that delivers improved performance, functionality, scalability and security. Designed to meet the expectations of end users for simple and interoperable management of modern scalable platform hardware, Redfish takes advantage of widely-used technologies to speed implementation and help system administrators be more effective.<!--more-->

With Redfish being a REST-based interface utilizing JSON and OData for systems management aims to replace Intelligent Platform Management Interface (IPMI), a widely used out-of-band specification developed in the late ‘90s. Like most systems manufacturers, Seagate supports IPMI and will continue to support it as a critical standard in the data center in lieu of broad adoption of Redfish. Where IPMI strains to meet the requirements of today’s massive multiscale environments, Redfish addresses IPMI inadequacies of interoperability, security, simplicity and scalability.

Redfish is developed by the DMTF’s [Scalable Platforms Management Forum](http://www.dmtf.org/standards/spmf) (SPMF). As a supporting member, Seagate, works alongside other leading systems manufacturers to create and publish this open industry standard specification and schema. This forum is led by Broadcom, Dell, Emerson, HP, Intel, Lenovo, Microsoft, Supermicro and VMware with additional support from AMI, Oracle, Fujitsu, Huawei, Mellanox and Seagate.

Redfish 1.0 feature set summary:

**Retrieve “IPMI class” data**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Basic server identification and asset info</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Health state</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Temperature sensors and fans</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Power supply, power consumption and thresholds</span>
</li>

**Discovery**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Service endpoint (network-based discovery)</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">System topology (rack/chassis/server/node)</span>
</li>

**Basic I/O infrastructure data**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Host NIC MAC address(es) for LOM devices</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Drive status / fault reporting</span>
</li>

**Security**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Session-based and leverages HTTPS</span>
</li>

**Perform Common Actions**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Reboot / power cycle server</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Change boot order / device</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Set power thresholds</span>
</li>

**Access and Notification**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">Serial console access via SSH</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Alert / event notification method(s)</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Event Log access method(s)</span>
</li>

**BMC infrastructure**

<li style="font-weight: 400;">
  <span style="font-weight: 400;">View / configure BMC network settings</span>
</li>
<li style="font-weight: 400;">
  <span style="font-weight: 400;">Manage local BMC user accounts</span>
</li>

Redfish 1.0 is only the beginning. Seagate and other industry leaders are already engaging within the DMTF Scalable Platform Management Forum on enhancements beyond Redfish 1.0 standard. You’re invited to [join](http://www.dmtf.org/join/spmf) the discussion or provide feedback through the DMTF submission portal. Comments and requirements from Redfish consumers are openly solicited and crucial to helping the SPMF prioritize capabilities in the upcoming next versions.

What does Redfish mean for Seagate partners and customers? It means a new level of control, management and monitoring for the data center, using a modern, secure RESTful API that is commonly understood and will be widely supported. We’ll further discuss Redfish’s concepts and constructs in this blog series, so stay tuned as we begin to showcase our adoption of Redfish initially within our suite of systems management software.