---
id: 787
title: 'Protocol Comparison: NETCONF versus Cisco WSMA'
date: 2010-01-08T14:45:47+00:00
author: Lee
excerpt: "Herein lies a comparison of two similar, embedded network configuration management protocols: Cisco's Web Services Management Agent (WSMA) and NETCONF. This comparative analysis is broken down into different functional categories, each containing a category winner (based on my own opinion). This analysis is taken from a Cisco device-centric perspective."
layout: post
guid: http://gingergeek.com/?p=787
permalink: /2010/01/protocol-comparison-netconf-versus-cisco-wsma/
dsq_thread_id:
  - "4747852120"
categories:
  - netconf
  - network management
  - wsma
tags:
  - cisco
  - netconf
  - wsma
---
Herein lies a comparison of two similar, embedded network configuration management protocols: Cisco’s Web Services Management Agent (WSMA) and NETCONF. This comparative analysis is broken down into different functional categories, each containing a category winner (based on my own opinion). This analysis is taken from a Cisco device-centric perspective.

<!--more-->

#### Category: Overall

**WSMA** (<span style="color: #000080;">Category Winner</span>)

  * NETCONF does configuration only. WSMA does all that NETCONF does and more like Exec commands and generic file system operations. NETCONF does, however, allow for server-initiated notification (of configuration changes) subscriptions, whereas this functionality is still on the WSMA roadmap. Server-intiated notification subscriptions are important in large networks of intermittently connected devices and in environments in which managed devices must reverse the management connection, punching holes through firewalls/network address translators.
  * NETCONF schema is a standard. WSMA schemas are proprietary.
  * NETCONF supports more transport protocols than WSMA.
  * From a Cisco perspective, NETCONF has no future roadmap, whereas WSMA has a future evolution. NETCONF is in IOS 12.4(9)T, WSMA is 12.4(24)T and 15.0.
  * NETCONF has been in the field a longer time, but it is less powerful. Assuming your managed network device supports WSMA, it’s the way to go.

#### Category: Protocol Support

**NETCONF** (<span style="color: #000080;">Category Winner</span>)

NETCONF supports the following transport protocols for transmission of it’s XML encoded data:

  * Console
  * Secure Shell – SSH v2-only (RFC 4742)
  * Simple Object Access Protocol (SOAP) over HTTP(S) RFC 4743
  * Blocks Extensible Exchange Protocol (BEEP) RFC 4744 – _technically superior, but is not widely adopted._
  * Transport Layer Security (TLS) RFC 5539

**WSMA**
  
WSMA supports the following transport protocols for transmission of it’s SOAP encapsulated XML encoded data:

  * Console
  * Secure Shell (SSH v2-only)
  * Simple Object Access Protocol (SOAP) over HTTP(S)
  * Transport Layer Security (TLS)

#### Category: Operations

**WSMA** (<span style="color: #000080;"><em>Category Winner</em></span>)

<div style="float: right;">
  <table class="dbx-box" style="border: 2px dashed lightgray;">
    <tr>
      <td colspan="3">
        <h4 class="dbx-handle" style="font-size: 1em;">
          Transport Protocol Support Matrix
        </h4>
      </td>
    </tr>
    
    <tr>
      <td align="center" width="60px">
        <strong>Protocol</strong>
      </td>
      
      <td align="center">
        <strong>NETCONF</strong>
      </td>
      
      <td align="center">
        <strong>WSMA</strong>
      </td>
    </tr>
    
    <tr>
      <td align="right">
        Console
      </td>
      
      <td align="center">
        <img class="size-full wp-image-736 aligncenter" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        SSH
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        HTTP
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-737" title="error" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="error" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        HTTPS
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-737" title="error" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="error" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        TLS
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        BEEP
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-736" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/check.gif?resize=24%2C24" alt="" data-recalc-dims="1" />
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-737" title="error" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/error.gif?resize=24%2C23" alt="error" data-recalc-dims="1" />
      </td>
    </tr>
    
    <tr>
      <td align="right">
        Telnet
      </td>
      
      <td align="center">
        <img class="aligncenter size-full wp-image-737" title="error" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/error.gif?resize=24%2C23" alt="error" data-recalc-dims="1" />
      </td>
      
      <td>
        <img class="aligncenter size-full wp-image-737" title="error" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2009/11/error.gif?resize=24%2C23" alt="error" data-recalc-dims="1" />
      </td>
    </tr>
  </table>
</div>

WSMA operations are supported through the following four agents:

  * _config_—Validates and applies a set of configuration commands to Cisco IOS software.
  * _exec_—Handles the EXEC-mode command-line operations on Cisco IOS software.
  * _filesys_ – Copies and validates files between local and remote file systems.
  * _notification_ – Collects configuration-change events and forwards the details to the management application, which is configured to receive the notifications. Notification subscriptions are bound to a single stream for the lifetime of the subscription.

**NETCONF**

  * _get_ – Retrieve running configuration and device state information.
  * _get-config, edit-config, copy-config_ – Create or replace an entire configuration datastore with the contents of another complete configuration datastore.
  * _delete-config_ – Delete a configuration datastore. The running configuration datastore cannot be deleted.
  * _lock_ – operation allows the client to lock the configuration system of a device.
  * _unlock_ – operation is used to release a configuration lock, previously obtained with the _lock_ operation.
  * _close-session_ – Request graceful termination of a NETCONF session.
  * _kill-session_ – Force the termination of a NETCONF session.
  * _create-subscription_ – Initiates an event notification subscription that will send asynchronous event notifications of any configuration change to the subscriber until the subscription terminates.

**Interest by Search Volume**

Interestingly, but not surprisingly, information regarding NETCONF is more highly sought after (at least according to the number of Google searches) than is information on WSMA.

<div align="center">
</div>