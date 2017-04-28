---
id: 1235
title: 'Contributing to Prometheus: An Open Source Tutorial'
date: 2016-06-12T12:30:35+00:00
author: Lee
excerpt: Recently adopted by the Cloud Native Computing Foundation, Prometheus is an open-source systems monitoring and alerting toolkit, focused on supporting the operation of microservices and containers. Like any open source project, it can be augmented with additional capabilities.
layout: post
guid: http://blog.gingergeek.com/?p=1235
permalink: /2016/06/contributing-to-prometheus-an-open-source-tutorial/
dsq_thread_id:
  - "4904852781"
image: /wp-content/uploads/2016/06/photo-1460804198264-011ca89eaa43.jpg
categories:
  - containers
  - how-to articles
  - systems management
tags:
  - metrics
  - prometheus
  - time series
---
[<img class="alignleft wp-image-1236 size-medium" src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/06/photo-1460804198264-011ca89eaa43.jpg?resize=300%2C209" alt="photo-1460804198264-011ca89eaa43" data-id="1236" srcset="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/06/photo-1460804198264-011ca89eaa43.jpg?resize=300%2C209 300w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/06/photo-1460804198264-011ca89eaa43.jpg?w=640 640w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/06/photo-1460804198264-011ca89eaa43.jpg)Recently [adopted](http://thenewstack.io/cloud-native-computing-foundation-prometheus-second-hosted-project/){.local-link} by the Cloud Native Computing Foundation, <a class="ext-link" href="http://www.prometheus.io/" rel="external nofollow">Prometheus</a> is an open-source systems monitoring and alerting toolkit, focused on supporting the operation of microservices and containers. Like any open source project, it can be augmented with additional capabilities.

Contributing to Prometheus is no different than most other open source endeavors, which, like many projects, welcomes <a class="ext-link" href="https://prometheus.io/community/" rel="external nofollow">community contributions</a>. Let’s gain better familiarity with the process by augmenting Prometheus’ <a class="ext-link" href="https://github.com/prometheus/alertmanager" rel="external nofollow">Alert Manager</a> with a new “history” view. The first step, naturally, is to check out the contributing guidelines for the specific repository (in this case, <a class="ext-link" href="https://github.com/prometheus/alertmanager/blob/master/CONTRIBUTING.md" rel="external nofollow">Alert Manager</a>‘s).

When electing to contribute to any open source project, you’ll want to ensure that you are capable of wielding the technologies used with the project — in this case, those are Go, AngularJS, SQL, etc. <!--more-->

The AlertManager component handles alerts sent by client applications such as the Prometheus server, carefully de-duplicating, correlating, and routing their notifications to their appropriate receiver (e.g. email, webhook, etc.). Current behavior of this component is only to display actively firing alerts.

Read more on [The New Stack](http://thenewstack.io/contributing-prometheus-history-alertmanager/)…