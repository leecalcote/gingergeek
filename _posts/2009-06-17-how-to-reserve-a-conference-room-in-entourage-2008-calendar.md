---
id: 299
title: How to reserve a conference room in Entourage 2008 Calendar
date: 2009-06-17T21:51:01+00:00
author: Lee
excerpt: "While Entourage does not support the same resource booking functionality that Outlook does, I’m able to successfully schedule conference rooms in Entourage. Here's how."
layout: post
guid: http://gingergeek.com/?p=299
permalink: /2009/06/how-to-reserve-a-conference-room-in-entourage-2008-calendar/
articleimg:
  - http://gingergeek.com/wp-content/uploads/2009/06/Entourage-Resource-Booking-200.png
dsq_thread_id:
  - "4785928250"
categories:
  - entourage
  - how-to articles
  - mac
tags:
  - calendaring
  - entourage
  - how-to
  - mac
---
I have heard variations of this question asked over and over:


<span style="position:relative;float:left;padding-right:5px;"> </span> 

<table border="0" align="right">
  <tr>
    <td>
      <blockquote style="text-align: center; width: 80%;">
        <p>
          How do I make a resource reservation in Entourage?
        </p>
      </blockquote>
    </td>
  </tr>
  
  <tr>
    <td align="center">
      …or similarly…
    </td>
  </tr>
  
  <tr>
    <td>
      <blockquote style="width: 80%; text-align: center;">
        <p>
          How do I schedule a meeting room in Entourage?
        </p>
      </blockquote>
    </td>
  </tr>
</table>

While Entourage <a href="http://www.entourage.mvps.org/exchange/compare.html" target="_blank">does not support</a> the same resource booking functionality that Outlook does, I’m able to _successfully schedule conference rooms, including Cisco Telepresence rooms_ in Entourage <!--more-->by simply placing the resource’s address into the To: field of a meeting request. I’m able to view the resource’s availability beforehand just as I do for any other attendee (denoted by the 

<span style="color: #ff9900;">orange rectangle</span>). The resource in this sample event is “AST06-2-Luckenbach (16)”.

 

<div id="attachment_322" style="width: 296px" class="wp-caption alignright">
  <a href="http://gingergeek.com/2009/06/how-to-reserve-a-conference-room-in-entourage-2008-calendar/entourage-resource-booking/" rel="attachment wp-att-322"><img class="size-medium wp-image-322" title="Entourage Resource Booking" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Resource-Booking.jpg?resize=286%2C300" alt="Entourage Resource Booking" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Resource-Booking.jpg?resize=286%2C300 286w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Resource-Booking.jpg?w=696 696w" sizes="(max-width: 286px) 100vw, 286px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Entourage Resource Booking
  </p>
</div>

The missing resource booking functionality here is:

  1. the automatic entry of the resource name into the Location field (denoted by the <span style="color: #ffff00;">yellow arrow</span>)
  2. the ability to use counter-proposals received by others who may wish to reschedule the meeting time. You need to do this manually.

<div id="attachment_335" style="width: 344px" class="wp-caption alignright">
  <a href="http://gingergeek.com/2009/06/how-to-reserve-a-conference-room-in-entourage-2008-calendar/entourage-meeting-request-accepted/" rel="attachment wp-att-335"><img class="size-full wp-image-335" title="Entourage Meeting Request Accepted" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Meeting-Request-Accepted.jpg?resize=334%2C44" alt="Entourage Meeting Request Accepted" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Meeting-Request-Accepted.jpg?w=334 334w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/06/Entourage-Meeting-Request-Accepted.jpg?resize=300%2C39 300w" sizes="(max-width: 334px) 100vw, 334px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Entourage Meeting Request Accepted
  </p>
</div>

The environment setup here is:

  1. Entourage 2008
  2. Exchange 2003
  3. Auto Accept Agent (not absolutely necessary, but highly recommended)

Contrary to what some might believe, your Exchange server does not need to be running the Auto Accept Agent for resource booking to work, but it sure is recommended. WIthout the Auto Accept Agent running, someone will have to manage meeting invitations manually for all resources.

I’m surprised others haven’t pointed out this functionality on how to schedule resources in Entourage out already. There seems to be many references pointing Entourage’s missing calendaring functionality. When I saw the University of Tennessee Knoxville IT department’s answer to “<a href="http://oit.utk.edu/helpdesk/kb/entry/292/" target="_blank">Can I schedule shared resources such as a conference room?</a>” I was particularly humored.

This procedure works for scheduling **Cisco Telepresence** rooms, too. You simply need to reserve rooms at both ends of the call (or all ends of the call in the case of multipoint conferences). If you cannot view a resource’s availability when looking at the Scheduling tab, you may want to [Troubleshoot Free/Busy Times in Microsoft Entourage](http://gingergeek.com/2009/11/troubleshooting-freebusy-times-in-microsoft-entourage/).