---
id: 6
title: How To Archive Entourage 2008 Mail using Multiple Identities
date: 2009-06-10T07:44:22+00:00
author: Lee
excerpt: The measly 350MB mailbox quota allotted by my corporate IT department has me being creative with the storage of my email. Many of the other information workers I know suffer the same plight. If you are a Microsoft Entourage (the Mac OS X cousin to Microsoft Outlook) like me, I hope this how-to helps assuage your mail storage, archival and backup woes.
layout: post
guid: http://gingergeek.com/?p=6
permalink: /2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/
articleimg:
  - http://gingergeek.com/wp-content/uploads/2009/06/export-entourage-mail-to-rge-archive-200.png
dsq_thread_id:
  - "4751809671"
categories:
  - entourage
  - how-to articles
  - mac
tags:
  - archive
  - backup
  - entourage
---
<div style="position:relative;float:left;padding-left:5px;">
  <span style="position:relative;float:left;padding-right:5px;"> </span>
</div>

<p style="text-align: justify;">
  The measly 350MB mailbox quota allotted by my corporate IT department has me being creative with the storage of my email. Many of the other information workers I know suffer the same plight. If you are a Microsoft Entourage (the Mac OS X cousin to Microsoft Outlook) like me and like to avoid paying for tools (like <a title="Entourage Email Archive X by Softhing" href="http://www.softhing.com/eeax.html" target="_blank" rel="nofollow">EEAX</a> or <a href="http://www.mailsteward.com/" target="_blank" rel="nofollow">MailSteward</a>), I hope this how-to helps assuage your mail storage, archival and backup woes. In my opinion, how to <a title="Archive Your Data by MS Entourage Help" href="http://www.entourage.mvps.org/database/archive.html" target="_blank" rel="nofollow">Archive Your Data</a> by Microsoft Entourage Help and other articles like “<a title="In Entourage, how do I archive my mail?" href="http://kb.iu.edu/data/atks.html" target="_blank" rel="nofollow">In Entourage, how do I archive my mail?</a>” do a mediocre job of informing us about the caveats involved in archiving mail. The two native export options I’ll speak of are:
</p>

<!--more-->

  1. archive Entourage mail using mbox files 
      * an mbox file contains a set of mail messages that you can import back into Entourage or into some other mail applications.
  2. archive Entourage mail using .rge archives 
      * an Entourage archive file (<a href="http://www.entourage.mvps.org/video/Import_rge/index.html" target="_blank" rel="nofollow">.rge</a>) can contain email messages, contacts, events, notes, tasks, and project files.
      * .rge files have high compression ratios, which saves on your disk space.

I promulgate using the latter of these options to archive your Entourage mail is the solution of choice and here’s how I suggest doing so:

## **Suggested Solution**

To clean up your mailbox in a comprehensive Time Machine and Spotlight-friendly way, use a combination of _Mail Views_ (Saved Searches), a _.rge archive_ and _multiple identities_. To ready your mail for archiving, you’ll first want to organize mail for export. Entourage will export data, but in a limited number of ways. One way to do this is by creating and assigning a category to your mail. Like others before me, I’ve chosen to archive my mail on an annual basis (I don’t know why, since I reach my mail quota well ahead of reaching the end of the year – I may need to archive every 6 months).

#### 1. Use Categories to Organize Email for Export

<div id="attachment_168" style="width: 160px" class="wp-caption alignright">
  <a rel="attachment wp-att-168" href="http://gingergeek.com/2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/mail-views-for-received-and-sent-archives/"><img class="size-thumbnail wp-image-168" title="mail-views-for-received-and-sent-archives" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/mail-views-for-received-and-sent-archives.png?resize=150%2C64" alt="Mail Views for Received and Sent Archives" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Mail Views for Received and Sent Archives
  </p>
</div>

<p style="padding-left: 30px; ">
  I suggest creating two custom Mail Views (last group in the folders pane, below Microsoft News Server) one for Received Mail and for Sent Mail.
</p>

  1. To create a mail view for Received Mail, select the folder you want to search in (probably your **Inbox)**, then go to to **Edit > Advanced Search** (⌥⌘ F)
  2. Set the option to **“Match if any criteria are met”**
  3. From the dropdown, set **“Date Received”**
  4. From the next dropdown, set **“Greater Than”** and then enter the preferred email age. This will find all email older than the specified number of days in the date received field. In the example screenshot, I was 151 days into the 365 day year when creating this archive.
<div id="attachment_167" style="width: 310px" class="wp-caption alignright">
  <a rel="attachment wp-att-167" href="http://gingergeek.com/2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/mail-view-to-archive-email-by-date-sent/"><img class="size-medium wp-image-167" title="mail-view-to-archive-email-by-date-sent" src="https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/mail-view-to-archive-email-by-date-sent.png?resize=300%2C60" alt="Mail View to Archive Email by Date Sent" srcset="https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/mail-view-to-archive-email-by-date-sent.png?resize=300%2C60 300w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/mail-view-to-archive-email-by-date-sent.png?w=557 557w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Mail View to Archive Email by Date Sent
  </p>
</div>

  5. Entourage will find all the matching mail. Scroll through and make sure all the mail you want is in the view and from all the folders you wish to archive. Save the search.
  6. Repeat steps 1-5 for your Sent Items using the parameters **“Date Sent”, “Greater Than”, <number of days>”**.

<div id="attachment_169" style="width: 160px" class="wp-caption alignright">
  <a rel="attachment wp-att-169" href="http://gingergeek.com/2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/saved-search-entourage-mail-view/"><img class="size-thumbnail wp-image-169" title="Setting Category on Entourage Mail" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/saved-search-entourage-mail-view.png?resize=150%2C150" alt="Setting Category on Entourage Mail" srcset="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/saved-search-entourage-mail-view.png?resize=150%2C150 150w, https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/saved-search-entourage-mail-view.png?zoom=2&resize=150%2C150 300w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Setting Category on Entourage Mail
  </p>
</div>

#### 2. Create an “Archive” Category

<p style="padding-left: 30px;">
  Once you’ve verified these two mail views to filter out the mail you wish to archive, create a new category to put them in.
</p>

  1. Go to **Edit > Categories > Edit Categories** and edit your categories to make an **“Archive”** category
  2. Right-click on your Mail Views, then assign your new category **“Archive”** to those items.

#### 3. Export Mail to .rge Archive

  1. Go to **File > Export**
  2. Select the option to export **“Items that are in a category”**.
  3. Choose your custom **“Archive”** category. Then select the item types, mail, tasks, etc., that you want to archive

<table border="0">
  <tr>
    <td>
      <span style="position:relative;float:left;padding-right:5px;"> </span>
    </td>
    
    <td>
      <p>
        <div id="attachment_166" style="width: 160px" class="wp-caption alignright">
          <a rel="attachment wp-att-166" href="http://gingergeek.com/2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/export-entourage-mail-to-rge-archive/"><img class="size-thumbnail wp-image-166" title="export-entourage-mail-to-rge-archive" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/export-entourage-mail-to-rge-archive.png?resize=150%2C150" alt="Export Entourage Mail to rge Archive" srcset="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/export-entourage-mail-to-rge-archive.png?resize=150%2C150 150w, https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/export-entourage-mail-to-rge-archive.png?zoom=2&resize=150%2C150 300w, https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/export-entourage-mail-to-rge-archive.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
          
          <p class="wp-caption-text">
            Export Entourage Mail to rge Archive
          </p>
        </div></td> 
        
        <td>
          <p>
            <div id="attachment_162" style="width: 160px" class="wp-caption alignright">
              <a rel="attachment wp-att-162" href="http://gingergeek.com/2009/06/how-to-archive-entourage-2008-mail-using-multiple-identities/delete-entourage-archived-rge-mail/"><img class="size-thumbnail wp-image-162" title="Delete Entourage Archived .rge Mail" src="https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/delete-entourage-archived-rge-mail.png?resize=150%2C150" alt="Delete Entourage Archived .rge Mail" srcset="https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/delete-entourage-archived-rge-mail.png?resize=150%2C150 150w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/delete-entourage-archived-rge-mail.png?zoom=2&resize=150%2C150 300w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2009/06/delete-entourage-archived-rge-mail.png?zoom=3&resize=150%2C150 450w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" /></a>
              
              <p class="wp-caption-text">
                Delete Entourage Archived .rge Mail
              </p>
            </div></td> </tr> </tbody> </table> 
            
            <h4>
              4. Create Another Identity
            </h4>
            
            <p>
              If you want quick access to your archived mail, I suggest creating a new Identity that will allow you to quickly “Switch Identities” to view old mail.
            </p>
            
            <table class="example" border="0">
              <tr>
                <td width="50%" valign="top">
                  <h5>
                    Identity Creation Option 1
                  </h5>
                  
                  <ol>
                    <li>
                      Go to your <strong>~/Documents/Microsoft User Data/Office 2008 Identities/your identity</strong>
                    </li>
                    <li>
                      Your Identity is named <strong>Main</strong> by default.
                    </li>
                    <li>
                      Duplicate your current Identity and rename it. Now, you have a duplicate Identity folder structure with your old mail that you can quickly switch to for easy searching.
                    </li>
                    <li>
                      Remove old mail messages from your current Identity using a <a href="#createmailview">custom Mail View</a>. You may wish to leave at least 60 days of old mail. You will have some duplicates but this may be preferable to switching Identities constantly to find recent mail.
                    </li>
                  </ol>
                </td>
                
                <td style="padding-left:5px;" valign="top">
                  <h5>
                    Identity Creation Option 2
                  </h5>
                  
                  <ol style="text-align: left;">
                    <li>
                      Go to <strong>Entourage > Switch Identity</strong>
                    </li>
                    <li>
                      Select <strong>“New”</strong>
                    </li>
                    <li>
                      Choose a name for your new identity and click <strong>“Next”</strong>
                    </li>
                    <li>
                      Skip the Assistant that comes up to import any files or set email account options.
                    </li>
                    <li>
                      Go to <strong>File > Import</strong>
                    </li>
                    <li>
                      Choose <strong>“Entourage information from an archive or earlier version”</strong>
                    </li>
                    <li>
                      Choose <strong>“Entourage archive (.rge)”</strong>
                    </li>
                    <li>
                      Select the .rge archive file that you have exported from Entourage and allow Entourage to import the archive
                    </li>
                  </ol>
                  
                  <p>
                    You may want to drag and drop your folders from the auto-created Archive.rge folder into folders within your existing Inbox structure.</td> </tr> </tbody> </table> 
                    
                    <div>
                    </div>
                    
                    <p>
                      Now you can switch back and forth between identities (Switch Identities ⌥⌘ Q) if you want to access an archive. Here’s why using the latter two solutions are a poor choice:
                    </p>
                    
                    <h2>
                      <strong>Alternative Solution</strong>
                    </h2>
                    
                    <ol>
                      <li>
                        Create a <a href="custommailview">custom Mail View</a> you can drag any view out of Entourage to create an .mbox file of the messages in that view.
                      </li>
                    </ol>
                    
                    <p>
                      <img class="size-full wp-image-192 alignnone" title="caution-sign-small" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/caution-sign-small.gif?resize=48%2C60" alt="caution-sign-small" align="middle" data-recalc-dims="1" /> <em>The message Received timestamp is lost on export.</em>
                    </p>
                    
                    <p>
                      Use a combination of Mail Views and MBOX file(s). Once your mail is organized into a categorical, meaningful saved searched, simply click and drag the view to your desktop. This creates an MBOX file (which can be opened with a text editor if you don’t mind reading through Internet headers in your mail and HTML converted to plain-text). Dragging mail to an MBOX file does not remove the mail from your mailbox. If you want to free up space in your mailbox, you’ll need to delete the contents of your Mail View separately.
                    </p>
                    
                    <p>
                      <img class="size-full wp-image-255 alignleft" title="tip" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2009/06/tip.png?resize=48%2C48" alt="tip" align="middle" data-recalc-dims="1" /><em>Drag your MBOX files into a new Identity, then switch Identities to search old mail. This keeps your regular database lean and more responsive.</em>
                    </p>