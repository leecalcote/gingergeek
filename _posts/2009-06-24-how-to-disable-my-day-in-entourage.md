---
id: 436
title: How to disable My Day in Entourage
date: 2009-06-24T23:54:50+00:00
author: Lee
excerpt: |
  When you install Microsoft Office 2008 for Mac, My Day conveniently adds itself to your list of applications to start up at login and pops-up in the upper-right hand corner of your screen each time you log into your Mac. If you'd like to get prevent My Day from starting up at login there are a couple ways to get rid of it.
layout: post
guid: http://blog.gingergeek.com/?p=436
permalink: /2009/06/how-to-disable-my-day-in-entourage/
articleimg:
  - http://blog.gingergeek.com/wp-content/uploads/2009/06/Entourage-My-Day-Logon-Preferences-200.png
dsq_thread_id:
  - "4744291179"
categories:
  - entourage
  - how-to articles
  - mac
tags:
  - entourage
  - how-to
  - mac
---
<div style="position:relative;padding: 0px 20px 20px 0px;">
  <span style="position:relative;float:left;padding-right:5px;"> </span>
</div>

When you install Microsoft Office 2008 for Mac, My Day conveniently adds itself to your list of applications to start up at login and pops-up in the upper-right hand corner of your screen each time you log into your Mac. If you’d like to get prevent My Day from starting up at login there are a couple ways to get rid of it.<!--more-->

How to _hide_ Entourage’s My Day:

<ol class="ollist" style="margin-left:45%">
  <li>
    To hide My Day, press Control+M.
  </li>
</ol>

How to _turn off_ Entourage’s My Day:

<ol class="ollist">
  <li>
    Right-click (Ctrl+click) on the My Day icon in the dock, then uncheck Open at Login.<br /> …or, if this doesn’t work…
  </li>
  <li>
    To prevent My Day from starting at login, open My Day preferences (CMD+, or the preferences icon in the bottom, right corner of My Day). Uncheck “Open at computer logon”.<br /> …or, if this doesn’t work…
  </li>
  <li>
    Trash My Day’s plist file, com.microsoft.myday.plist, found under Hard Drive/Users/(your user)/Library/Preferences
  </li>
</ol>

<div id="attachment_439" style="width: 160px" class="wp-caption alignright">
  <a rel="attachment wp-att-439" href="http://blog.gingergeek.com/2009/06/how-to-disable-my-day-in-entourage/entourage-my-day-logon-preferences/"><img class="size-thumbnail wp-image-439" title="Entourage My Day - Logon Preferences" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Entourage-My-Day-Logon-Preferences.png?resize=150%2C150" alt="System Preferences -- data-recalc-dims="1"> Accounts --> Login Items" width="150" height="150" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Entourage-My-Day-Logon-Preferences.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Entourage-My-Day-Logon-Preferences.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Entourage-My-Day-Logon-Preferences.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" /></a>
  
  <p class="wp-caption-text">
    System Preferences --> Accounts --> Login Items
  </p>
</div>

To verify My Day has been turned off, open Login Items under Account in System Preferences.

My Day has a preference to either show its icon in the Dock or to show in the Mac OS menu bar. If you’re having difficulty getting one or the other preference to stick when changing the My Day icon location, note that your user account will need write permission to My Day’s Application folder found under /Applications/Microsoft Office 2008/Office/My Day.app/. Admin user accounts have this write permission by default. Standard user account will have read-only permission to this folder.