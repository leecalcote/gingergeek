---
id: 869
title: 'Going Native with OpenStack Centric Applications: Overview'
date: 2014-11-17T00:39:04+00:00
author: Lee
excerpt: 'Cloud infrastructure is useless without applications running atop, providing business serviOpenStack Applicationsces and solving customer needs. So, as applications ascend to the throne as the rightful king of cloud, focus sharpens on their support within OpenStack-based clouds. '
layout: post
guid: http://gingergeek.com/?p=869
permalink: /2014/11/going-native-with-openstack-centric-applications-overview/
articleimg:
  - http://gingergeek.com/wp-content/uploads/2014/11/OpenStack-Applications-300x300.png
dsq_thread_id:
  - "4760993034"
image: /wp-content/uploads/2014/11/OpenStack-Applications.png
categories:
  - openstack
tags:
  - docker
  - heat
  - merlin
  - murano
  - openstack
  - puppet
  - solum
---
Cloud infrastructure is useless without applications running atop, providing business servi[<img class="alignleft wp-image-868 size-thumbnail" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Applications.png?resize=150%2C150" alt="OpenStack Applications" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Applications.png?resize=150%2C150 150w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Applications.png?resize=300%2C300 300w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Applications.png?w=697 697w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" />](http://gingergeek.com/2014/11/going-native-with-openstack-centric-applications-overview/openstack-applications/)ces and solving customer needs. So, as applications ascend to the throne as the rightful king of cloud, focus sharpens on their support within OpenStack-based clouds. With this focus, let’s walk through a survey of components and projects supporting applications in OpenStack, understanding what a day in the life of an application in OpenStack is like. We’ll start with an overview of the application ecosystem comprised of a number of supporting projects. In the ecosystem overview below, relevant OpenStack projects are presented in context of existing, similar technologies with which you may be familiar. These similar technologies both under and overlap functionality of the respective OpenStack project, but are shown to hasten your general understanding of which bucket these projects fall into by way of tech you may already know (so, add a pinch of salt when considering relevancy of suggested affiliated technologies).<!--more-->

### Application Ecosystem by Project

Like individual lines in a product family, projects within OpenStack engulf and extend one another for related, but distinct purposes and target use cases. OpenStack developers are cautious to apply DRY principles in their approach to project design, integrating functionality rather than reinventing the wheel as they go. The _Project Focus and Relationship_ diagram both figuratively and literally places project relationships into round bubbles, identifying conceptual starting points for the genesis of an application as well as the reuse of some projects by others.

  * **Application Blueprint Designer – <a href="https://wiki.openstack.org/wiki/Merlin" target="_blank">Merlin</a>** 
      * RavelloSystems, UrbanCode, CliQr, Prime Service Catalog*…
  * **Application Lifecycle Management PaaS – <a href="https://wiki.openstack.org/wiki/Solum" target="_blank">Solum</a>** 
      * Similar technologies (ALM) – Atlassian Suite, HP ALM, Cloudpipes, Serena…
      * Similar technologies (PaaS) – Openshift, Cloud Foundry, BlueMix, AppScale, Heroku, App Engine…
    
    <div id="attachment_887" style="width: 310px" class="wp-caption alignright">
      <a href="http://gingergeek.com/2014/11/going-native-with-openstack-centric-applications-overview/openstack-centric-applications-project-focus-and-relationship/"><img class="wp-image-887 size-medium" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Project-Focus-and-Relationship.png?resize=300%2C142" alt="OpenStack Centric Applications - Project Focus and Relationship" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Project-Focus-and-Relationship.png?resize=300%2C142 300w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Project-Focus-and-Relationship.png?resize=1024%2C487 1024w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Project-Focus-and-Relationship.png?w=1568 1568w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
      
      <p class="wp-caption-text">
        Project Focus and Relationship
      </p>
    </div></li> 
    
      * **Application Catalog – <a href="https://wiki.openstack.org/wiki/Murano" target="_blank">Murano</a>** 
          * Similar technologies – AppStack, CliQr, ITApp, AppDirect…
      * **Application Stack Provisioning – <a href="https://wiki.openstack.org/wiki/Heat" target="_blank">Heat</a>, Magnum** 
          * Similar technologies – AWS Elastic Beanstalk, Kubernetes, GearD, Warden, Fleet, MaestroNG, CliQr, Nirmata…
      * **Application Containers – <a href="https://wiki.openstack.org/wiki/Docker" target="_blank">Docker</a>** 
          * Similar technologies – OpenVZ, Linux V-Server, FreeBSD jails, AIX Workload Partitions and Solaris Containers
      * **Application Configuration Management – Puppet, Chef** 
          * Similar technologies – Heat, Salt, Ansible, <a href="https://wiki.openstack.org/wiki/Satori" target="_blank">Satori</a>*…</ul> 
    
    ### A Day in the Life of an OpenStack-Native Application
    
    The _Application Lifecycle Flows_ diagram defines different entrance points by which applications are birthed and the flow between different OpenStack projects within their lifecycle.
    
    <div id="attachment_878" style="width: 310px" class="wp-caption alignleft">
      <a href="http://gingergeek.com/2014/11/going-native-with-openstack-centric-applications-overview/openstack-centric-applications-application-lifecycle-flows/" rel="attachment wp-att-878"><img class="size-medium wp-image-878" src="https://i2.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Application-Lifecycle-Flows.png?resize=300%2C176" alt="OpenStack Centric Applications - Application Lifecycle Flows" srcset="https://i2.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Application-Lifecycle-Flows.png?resize=300%2C176 300w, https://i2.wp.com/gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Application-Lifecycle-Flows.png?resize=1024%2C603 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
      
      <p class="wp-caption-text">
        Application Lifecycle Flows
      </p>
    </div>
    
    Users may **design** applications with Merlin, **develop** applications with Solum, **order** applications with Murano, **deploy** applications and resources with Heat and **manage** applications with Puppet/other configuration managers.
    
    ### “Applications”
    
    Given that applications are varied in nature both in terms of their type and complexity, let’s take a moment to review their possible shapes and sizes. With regard to types of applications, some are  image-based and some are container-based while others are offered simply as a SaaS subscription (implying that a singular instance of this application may serve multiple tenants). Applications may be cloud-native (designed to be scaled out, highly distributed, service-oriented) or enterprise-architected (designed to be scaled up, designed with layers and functional domains). Application complexity ranges from single component (image or container) to multiple component, multiple environment, multiple OpenStack deployments to OpenStack and other systems. Applications may be comprised of multiple components (e.g. MySQL, PHP, Apache) or a singular components (MySQL). Application components may be distributed or contained within a given container, VM or cloud. With these possibilities in mind, let’s begin our survey of their support with the OpenStack-native application catalog – Murano in the next post in this series.