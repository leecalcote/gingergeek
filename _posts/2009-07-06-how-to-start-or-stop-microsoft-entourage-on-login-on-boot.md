---
id: 562
title: How to start or stop Microsoft Entourage on Login (on Boot)
date: 2009-07-06T22:36:37+00:00
author: Lee
excerpt: How to set Microsoft Entourage of Office 2008 for Mac automatically start on login into Mac OS X.
layout: post
guid: http://blog.gingergeek.com/?p=562
permalink: /2009/07/how-to-start-or-stop-microsoft-entourage-on-login-on-boot/
dsq_thread_id:
  - "4745755594"
categories:
  - entourage
  - how-to articles
  - mac
tags:
  - entourage
  - how-to
  - mac
  - tips
---
<blockquote style="width: 50%;">
  <p>
    How do I set Entourage to start on boot?
  </p>
</blockquote>

To have Microsoft Entourage automatically load when logging into Mac OS  X, you can check the “Open at Login” option by right-clicking 

<div id="attachment_565" style="width: 160px" class="wp-caption alignright">
  <a rel="attachment wp-att-565" href="http://blog.gingergeek.com/2009/07/how-to-start-or-stop-microsoft-entourage-on-login-on-boot/entourage-added-to-login-items/"><img class="size-thumbnail wp-image-565" title="Microsoft Entourage added to Login Items to auto start on login" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/07/Entourage-added-to-Login-Items.png?resize=150%2C150" alt="Entourage added to Login Items" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/07/Entourage-added-to-Login-Items.png?resize=150%2C150 150w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/07/Entourage-added-to-Login-Items.png?zoom=2&resize=150%2C150 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/07/Entourage-added-to-Login-Items.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Entourage added to Login Items
  </p>
</div>(CTRL+click) the Entourage icon while Entourage is open or its icon is in the Dock (at the bottom of your screen). Alternatively, to have Entourage auto start on login, through the Apple Menu –> System Preferences– > Accounts –> Login Items, add Microsoft Entourage to the list.

<!--more-->

<blockquote style="width: 50%;">
  <p>
    How do I stop Entourage from starting at login?
  </p>
</blockquote>

Use the same tools listed above to prevent Entourage from auto starting at login (by deselecting “Open at Login” or removing Entourage from the list of applications in Login Items).
  
<a rel="attachment wp-att-572" href="http://blog.gingergeek.com/2009/07/how-to-start-or-stop-microsoft-entourage-on-login-on-boot/entourage-open-at-login/"><img class="size-thumbnail wp-image-572" title="Microsoft Entourage Open at Login Option" src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/07/Entourage-Open-at-Login.png?resize=150%2C150" alt="Entourage "Open at Login" Option" data-recalc-dims="1" /></a>

<blockquote style="width: 50%;">
  <p>
    I removed Entourage from my Account’s Login Items list. Entourage still starts on login. What gives?
  </p>
</blockquote>

Another application is the likely culprit here. Applications with calendaring or scheduling functionality such as MenuCalendarClock are known to launch Entourage every time it checks for events. Some have found that Keyboard Maestro, Quicksilver, LaunchBar, iKey or EntourageABMenu have a similar effect on Entourage.