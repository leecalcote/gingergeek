---
id: 373
title: Create a Send to Mail Recipient in Mac OS X using Automator Workflow
date: 2009-06-19T22:00:07+00:00
author: Lee
excerpt: |
  Are you a Windows-convert and miss the ability to right-click on a file and choose "Send to Mail Recipient"? Look no further, Automator is here. I can't recall just how often I made use of Windows Explorer's context menu selection "Send Mail to Recipient", but know that it was enough to leave me wanting after switching to Mac OS X.
layout: post
guid: http://blog.gingergeek.com/?p=373
permalink: /2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/
articleimg:
  - http://blog.gingergeek.com/wp-content/uploads/2009/06/automator-200.jpg
dsq_thread_id:
  - "4747823917"
categories:
  - automator
  - entourage
  - how-to articles
  - mac
tags:
  - automator
  - entourage
  - how-to
  - mac
  - shortcuts
---
<img class="alignleft size-thumbnail wp-image-388" title="automator" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/automator.jpg?resize=58%2C58" alt="automator" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/automator.jpg?resize=150%2C150 150w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/automator.jpg?resize=300%2C300 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/automator.jpg?w=512 512w" sizes="(max-width: 58px) 100vw, 58px" data-recalc-dims="1" />

<div id="attachment_383" style="width: 160px" class="wp-caption alignright">
  <a rel="attachment wp-att-383" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/windows-send-to-mail-recipient-2/"><img class="size-thumbnail wp-image-383" title="Windows Send to Mail Recipient" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Windows-Send-to-Mail-Recipient1.png?resize=150%2C150" alt="Windows Explorer - Send to Mail Recipient" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Windows-Send-to-Mail-Recipient1.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Windows-Send-to-Mail-Recipient1.png?zoom=2&resize=150%2C150 300w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Windows Explorer - Send to Mail Recipient
  </p>
</div>

Are you a Windows-convert and miss the ability to right-click on a file and choose “Send to Mail Recipient”? Look no further, Automator is here. I can’t recall just how often I made use of Windows Explorer’s context menu selection “Send Mail to Recipient”, but know that it was enough to leave me wanting after switching to Mac OS X.

**This article applies to OS X 10.4 (Tiger) and OS X 10.5 (Leopard), not OS X 10.6 (Snow Leopard)**

Here’s how you can use an Automator workflow to create this same functionality in OS X Finder’s context menu.<!--more-->

  1. First, open Automator and choose to create a Custom workflow. 
    <div id="attachment_392" style="width: 160px" class="wp-caption alignnone">
      <a rel="attachment wp-att-392" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/automator-new-custom-workflow/"><img class="size-thumbnail wp-image-392 " title="Automator New Custom Workflow" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Automator-New-Custom-Workflow.png?resize=150%2C150" alt="New Automator Custom Workflow" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Automator-New-Custom-Workflow.png?resize=150%2C150 150w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Automator-New-Custom-Workflow.png?zoom=2&resize=150%2C150 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Automator-New-Custom-Workflow.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
      
      <p class="wp-caption-text">
        New Automator Custom Workflow
      </p>
    </div></li> 
    
      * Second, under the “Files and Folders” actions library, drag and drop Finder’s “Get Selected Items” to the righthand pane to begin building your workflow. 
        <div id="attachment_391" style="width: 160px" class="wp-caption alignnone">
          <a rel="attachment wp-att-391" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/action-finder-get-selected-items/"><img class="size-thumbnail wp-image-391 " title="Action - Finder Get Selected=" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Finder-Get-Selected-Items.png?resize=150%2C150" alt="Action - Finder Get Selected=" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Finder-Get-Selected-Items.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Finder-Get-Selected-Items.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Finder-Get-Selected-Items.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
          
          <p class="wp-caption-text">
            Action - Finder Get Selected Items
          </p>
        </div></li> 
        
          * Third, under the “Mail” actions library, drag and drop Entourage’s _Create New Mail Message_ (or Mail’s _New Mail Message_, if you prefer) to the righthand window pane. <div id="attachment_390" style="width: 160px" class="wp-caption alignnone">
              <a rel="attachment wp-att-390" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/action-create-new-entourage-mail-message/"><img class="size-thumbnail wp-image-390" title="Action - Create New Entourage Mail Message" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Create-New-Entourage-Mail-Message.png?resize=150%2C150" alt="Action - Create New Entourage Mail Message" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Create-New-Entourage-Mail-Message.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Create-New-Entourage-Mail-Message.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Create-New-Entourage-Mail-Message.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
              
              <p class="wp-caption-text">
                Action - Create New Entourage Mail Message
              </p>
            </div>
            
            <div style="position: relative;">
            </div>
        
          * Fourth, and finally, again under the “Mail” actions library, drag and drop Entourage’s _Add Attachments to Entourage Message_ (or Mail’s _Add Attachments to Front Message_) to the righthand window pane <div id="attachment_389" style="width: 160px" class="wp-caption alignnone">
              <a rel="attachment wp-att-389" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/action-add-attachments-to-entourage-messages/"><img class="size-thumbnail wp-image-389" title="Action - Add Attachments to Entourage Messages" src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Add-Attachments-to-Entourage-Messages.png?resize=150%2C150" alt="Action - Add Attachments to Entourage Messages" srcset="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Add-Attachments-to-Entourage-Messages.png?resize=150%2C150 150w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Add-Attachments-to-Entourage-Messages.png?zoom=2&resize=150%2C150 300w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Action-Add-Attachments-to-Entourage-Messages.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
              
              <p class="wp-caption-text">
                Action - Add Attachments to Entourage Messages
              </p>
            </div>
            
            .</li> </ol> 
            
            <div id="attachment_378" style="width: 160px" class="wp-caption alignright">
              <a rel="attachment wp-att-378" href="http://blog.gingergeek.com/2009/06/create-a-send-to-mail-recipient-in-mac-os-x-using-automator-workflow/workflow-context-menu-selection/"><img class="size-thumbnail wp-image-378" title="Workflow Context Menu Selection" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Workflow-Context-Menu-Selection.png?resize=150%2C150" alt="Workflow Context Menu Selection" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Workflow-Context-Menu-Selection.png?resize=150%2C150 150w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Workflow-Context-Menu-Selection.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/Workflow-Context-Menu-Selection.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
              
              <p class="wp-caption-text">
                Workflow Context Menu Selection
              </p>
            </div>
            
            Now that your workflow is complete, you’ll need to save it. I recommend first saving it as a “workflow”, so you can tweak it later if need be. Next, we’ll choose to save it as a Finder plugin, which will put your workflow plugin into ~/Library/Workflows/Applications/Finder/
            
            You can also save Automator workflows as applications (.app), however, doing so in this example would mean when you run the .app, Entourage will open and attach the .app file itself to your new mail message – not quite the intended use here.
            
            The only two negatives I can speak of with regard to using Automator workflows are:
  
            
<span style="position:relative;float:left;padding-right:5px;"> </span>
            
              1. Automator workflows may take a few seconds to execute. An AppleScript version of the same workflow executes more quickly, but of course means you’ll have to code the automation rather than click your way through creating it.
              2. The Automator workflows are three levels deep in the Finder context menu. This makes navigating your mouse to select your workflow precarious.
            
            <img class="alignright size-full wp-image-375" title="OS X Send to Mail Recipient" src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2009/06/OS-X-Send-to-Mail-Recipient.png?resize=102%2C89" alt="OS X Send to Mail Recipient" data-recalc-dims="1" />
  
            I can live with the extra few seconds to execute the workflow, but would love to see an automator workflow at the top level of the “More” contextual menu. Anyone know how this is done?