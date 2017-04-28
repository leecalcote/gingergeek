---
id: 701
title: Troubleshooting Free/Busy Times in Microsoft Entourage
date: 2009-11-21T23:52:46+00:00
author: Lee
excerpt: "Having trouble viewing free/busy times when scheduling meetings in the Microsoft Entourage calendar? If you cannot see other people's availability when inviting them to a meeting, you'll want to confirm the following settings..."
layout: post
guid: http://blog.gingergeek.com/?p=701
permalink: /2009/11/troubleshooting-freebusy-times-in-microsoft-entourage/
dsq_thread_id:
  - "4867705716"
categories:
  - entourage
  - how-to articles
  - mac
tags:
  - calendaring
  - entourage
  - mac
  - tips
---

<span style="position:relative;float:left;padding-right:5px;"> </span> Having trouble viewing free/busy times when scheduling meetings in the Microsoft Entourage calendar? If you cannot see other people’s availability when inviting them to a meeting, you’ll want to confirm the following settings…

<!--more-->

In short:

<div>
  <blockquote style="text-align:center;margin-left:45%;">
    <p>
      <strong>Make certain your account’s <em>Public Folders Server</em> field matches that of your <em>Exchange Server</em> field.</strong>
    </p>
  </blockquote>
</div>

<div id="attachment_705" style="width: 160px" class="wp-caption alignright">
  <a href="http://blog.gingergeek.com/2009/11/troubleshooting-freebusy-times-in-microsoft-entourage/microsoft-entourage-advanced-account-settings/"><img class="size-thumbnail wp-image-705  " title="Microsoft Entourage Advanced Account Settings" src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Microsoft-Entourage-Advanced-Account-Settings.png?resize=150%2C150" alt="Microsoft Entourage Advanced Account Settings" srcset="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Microsoft-Entourage-Advanced-Account-Settings.png?resize=150%2C150 150w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Microsoft-Entourage-Advanced-Account-Settings.png?zoom=2&resize=150%2C150 300w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Microsoft-Entourage-Advanced-Account-Settings.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Microsoft Entourage Advanced Account Settings
  </p>
</div>

In an Exchange environment when an Entourage 2004 user tries to schedule meetings with other users, availability information is retrieved using a WebDAV based query (Get /public/?Cmd=freebusy) to the Public Folder Server configured in your account settings under the advanced tab.

Entourage 2008 is able to also utilize ‘Exchange Web Services’ (available only on Exchange 2007 Server) to retrieve availability information. Public Folders are a feature of Microsoft Exchange Server that provide a way to collect, organize, and share information with others in an organization. Public folders are often used by project teams or user groups to share information about a common area of interest. You can use public folders in

<div id="attachment_706" style="width: 160px" class="wp-caption alignleft">
  <a href="http://blog.gingergeek.com/2009/11/troubleshooting-freebusy-times-in-microsoft-entourage/free-busy-availability-scheduling-in-microsoft-entourage/"><img class="size-thumbnail wp-image-706 " title="Free/Busy Availability Scheduling in Microsoft Entourage" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Free-Busy-Availability-Scheduling-in-Microsoft-Entourage-150x150.png?resize=150%2C150" alt="Free/Busy Availability Scheduling in Microsoft Entourage" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Free-Busy-Availability-Scheduling-in-Microsoft-Entourage.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Free-Busy-Availability-Scheduling-in-Microsoft-Entourage.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/11/Free-Busy-Availability-Scheduling-in-Microsoft-Entourage.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Free/Busy Availability Scheduling in Microsoft Entourage
  </p>
</div>

Entourage, to view and post messages, events and contacts. The Exchange server that stores Public Folders is also usually used to store users’ free/busy scheduling information. Having confirmed your Entourage Exchange account’s _Public Folders Server_ field matches that of your _Exchange Server_, you should now be able to see other user’s calendar availability, assuming your organization stores this free/busy time information in the public folder.

You should also be able to see resource/conference room availability. For an example of how to reserve resources, including Cisco Telepresence rooms, see [How-to Reserve a Conference Room in Entourage 2008](http://blog.gingergeek.com/2009/06/how-to-reserve-a-conference-room-in-entourage-2008-calendar/).