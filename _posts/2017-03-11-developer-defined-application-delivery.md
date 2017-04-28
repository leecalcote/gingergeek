---
id: 1740
title: Developer-defined application delivery
date: 2017-03-11T11:17:09+00:00
author: Lee
excerpt: Cloud-native applications are designed to draw upon the performance, scalability, and reliability benefits of distributed systems. Unfortunately, distributed systems often come at the cost of added complexity. As individual components of your application are distributed across networks, and those networks have communication gaps or experience degraded performance, your distributed application components need to continue to function independently.
layout: post
guid: http://blog.gingergeek.com/?p=1740
permalink: /2017/03/developer-defined-application-delivery/
dsq_thread_id:
  - "5623406169"
categories:
  - containers
  - microservices
  - network management
tags:
  - kubernetes
  - load-balancing
  - nginx
---
<div id="attachment_1741" style="width: 310px" class="wp-caption alignleft">
  <a href="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg"><img class="wp-image-1741 size-medium" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?resize=300%2C225" alt="" data-id="1741" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?resize=300%2C225 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?resize=768%2C576 768w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?resize=1024%2C768 1024w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?w=2000 2000w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2017/03/ship-84139.jpg?w=3000 3000w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Ship with tug (source: <a href="https://pixabay.com/en/ship-containers-products-shipping-84139/">tpsdave via Pixabay</a>).
  </p>
</div>

Cloud-native applications are designed to draw upon the performance, scalability, and reliability benefits of distributed systems. Unfortunately, distributed systems often come at the cost of added complexity. As individual components of your application are distributed across networks, and those networks have communication gaps or experience degraded performance, your distributed application components need to continue to function independently.

To avoid inconsistencies in application state, distributed systems should be designed with an understanding that components will fail. Nowhere is this more prominent than in the network. Consequently, at their core, distributed systems rely heavily on load balancing—the distribution of requests across two or more systems—in order to be resilient in the face of network disruption and horizontally scale as system load fluctuates.<!--more-->

As distributed systems become more and more prevalent in the design and delivery of cloud-native applications, load balancers saturate infrastructure design at every level of modern application architecture. In their most commonly thought-of configuration, load balancers are deployed in front of the application, handling requests from the outside world. However, the emergence of microservices means that load balancers play a critical role behind the scenes: i.e. managing the flow between services.

Therefore, when you work with cloud-native applications and distributed systems, your load balancer takes on other role(s):

Read the full article on [O’Reilly](https://www.oreilly.com/learning/developer-defined-application-delivery).