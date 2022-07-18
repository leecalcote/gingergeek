---
id: 1058
title: Kubernetes community gathers for inaugural European edition of KubeCon
date: 2016-03-24T13:57:53+00:00
author: Lee
excerpt: While a hot topic at various conferences, Kubernetes is the sole technological focus at KubeCon, a conference dedicated to education and community engagement of Kubernauts (Kubernetes enthusiasts).
layout: post
guid: http://gingergeek.com/?p=1058
permalink: /2016/03/kubernetes-community-gathers-for-inaugural-european-edition-of-kubecon/
dsq_thread_id:
  - "4749585553"
image: /wp-content/uploads/2016/03/DSC_0008.jpg
categories:
  - containers
tags:
  - containers
  - kubernetes
---
<img class="size-medium wp-image-1059 align left" title="" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/03/DSC_0008.jpg?resize=300%2C200" alt="DSC_0008" style="margin-right:.10in;margin-bottom:.05in;" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/03/DSC_0008.jpg?resize=300%2C200 300w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/03/DSC_0008.jpg?resize=768%2C511 768w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/03/DSC_0008.jpg?w=925 925w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />

<small><em>Originally posted on <a href="http://www.networkworld.com/article/3046063/open-source-tools/kubernetes-community-gathers-for-inaugural-european-edition-of-kubecon.html" target="_blank">Network World</a> on March 24th, 2016. </em></small>

For the uninitiated, <a title="Kubernetes" href="http://kubernetes.io/docs/whatisk8s/" target="new">Kubernetes</a> is an opinionated framework for building distributed systems or as its tagline states “an open source system for automating deployment, scaling, and operations of applications.” While a hot topic at various conferences, Kubernetes is the sole technological focus at KubeCon. KubeCon is a conference dedicated to education and community engagement of Kubernauts (Kubernetes enthusiasts).<!--more-->

Organized by KubeAcademy, KubeCon 2015 was the initial edition of this conference, launched back in November and held in San Francisco. With about 500 attendees, KubeCon EU 2016 was the inaugural European edition. The two-day community conference was held in London on March 10 and 11, 2016 with <a href="https://skillsmatter.com/conferences/7884-kubecon-london#venue" target="new">CodeNode</a> as the venue – well-suited for the number of attendees and sessions.

Not at all talks were strictly cluster manager focused. Some explored the intersection of traditional virtualization with virtual machines or configuration management and container-based workloads orchestrated by Kubernetes. Slides from all talks have been made <a href="http://www.slideshare.net/search/slideshow?lang=en&page=1&q=kubeacademy&qid=0465320c-6d5b-40b1-835a-25ec924e8a88&searchfrom=header&sort=relevance" target="new">available</a> as well as their recordings will soon be posted. Presenters and vendors at the conference confirmed the pace of innovation of this container orchestration system continues to move at an incredible clip. Users including New York Times, Met Office Informatics Lab, Pearson and others were not shy in bringing forward their stories.

In the week following KubeCon (on St. Patrick’s Day), Kubernetes 1.2 was released, touting 680 unique contributions to the project – the largest release yet. In coordination with this release was the relaunching of a redesigned <a href="http://kubernetes.io/" target="new">kubernetes.io</a> site launched to boot. <a href="http://blog.kubernetes.io/2016/03/Kubernetes-1.2-even-more-performance-upgrades-plus-easier-application-deployment-and-management-.html" target="new">Highlights of the 1.2 release</a> include:

  * **Scale improvements** – increased cluster scale by 400% to 1,000 nodes and 30,000 containers per cluster.
  * **Dynamic Configuration (ConfigMap API)** enables applications to pull their configuration when they run rather than packaging it in at build time.
  * **Turnkey Deployments** (Beta Deployment API) handles versioning, multiple simultaneous rollouts, aggregating status across all pods, maintaining application availability and rollback.
  * **Automated cluster management** 
      * Simplified application deployment and management.
  * **Kubedash** – a new UI allows for getting started quickly and accessing the same functionality found in the CLI.<figure class="large ">

[<img class="align center" src="https://i2.wp.com/images.techhive.com/images/article/2016/03/screen-shot-2016-03-22-at-2.28.46-pm-100651902-large.idge.png?w=90%25" alt="kubedash screenshot" data-recalc-dims="1" />](https://i2.wp.com/images.techhive.com/images/article/2016/03/screen-shot-2016-03-22-at-2.28.46-pm-100651902-large.idge.png)</figure> 

No sooner than 1.2 is published does the 1.3 roadmap take shape and tentatively scheduled for release ~16 weeks from now with the following highlights slated:

  * **Legacy application support** (Nominal Services aka [PetSet](https://github.com/kubernetes/kubernetes/pull/18016)) – aims to solve problems currently encountered with systems where the identities of nodes are important (primarily for different types of databases)
  * **Cluster Federation** (aka [Ubernetes](https://github.com/kubernetes/kubernetes/blob/8813c955182e3c9daae68a8257365e02cd871c65/release-0.19.0/docs/proposals/federation.md)) – will provide a real (perhaps preliminary) solution to cross-zone clusters (typically geographically distant clusters)
  * **Higher scale** – improving upon the 400% scale increase already delivered in 1.2. 
      * [Scale up to 250 pods per node](https://trello.com/c/fD83kRPE/102-remove-hard-coded-caps-and-use-back-pressure-in-the-system)
      * Scale out to 1000 nodes at half-max-pod-density
  * **In-cluster IAM** – Identity and Access Management will be added in the form of an [OIDC](http://openid.net/connect/) integration to distinguish between different types of users accessing a cluster
  * **Cluster auto-scaling**
  * **Scheduled job** – needed for performing all time-related actions, namely backups, report generation, etc.
  * **Public cloud dashboard** – with results of nightly runs across multiple cloud providers
  * **Storage** – improve dynamic provisioning of volumes 
      * [quotas for PersistentVolumes](https://trello.com/c/e85W63b1/113-enable-quotas-for-total-volume-size-across-all-pvs-ops-rfe)

Among other announcements at the conference was that of the Cloud Native Computing Foundation (part of the Linux Foundation) [accepting Kubernetes as its first hosted project](https://cncf.io/news/announcement/2016/03/cloud-native-computing-foundation-accepts-kubernetes-first-hosted-projec-0). Along with the acceptance of Kubernetes’ intellectual property (the entire Kubernetes code base), CNCF announced results of the election for members to the project’s Technical Oversight Committee. This list currently includes members from six different organizations, all of which either having significant doings with both advancing Kubernetes as well as their business models around the open source project.

Following the footsteps of Rackspace and Intel in putting together [two 1,000 node clusters for the OpenStack community](http://blog.rackspace.com/openstack-tokyo-day-1-two-1000-node-clusters-now-available-for-testing/) to develop and test at scale, next steps for the CNCF include establishing a 1,000 node cluster for the community to run and validate cloud native applications and infrastructure at scale.<aside id="" class="nativo-promo tablet desktop"></aside> 

Comments from those who attended and did not attend the conference indicators that KubeAcademy is acheiving their stated mission of fostering a community of Kubernetes developers and operators by providing education, training, and events. With some conference goers simply thrilled just to “…finally get a proper Kubernetes sticker for my laptop!!! Yaay!” and others setting “new professional goals to make it 2 the next KubeCon”, the conference was a success. Let’s hope [sponsor funding](https://kubecon.io/sponsors/) of the next KubeCon includes a livestream!

 