---
id: 899
title: 'Going Native with OpenStack Centric Applications: Murano'
date: 2014-11-18T23:44:39+00:00
author: Lee
excerpt: Murano is an OpenStack-native application catalog that allows application developers and cloud administrators to publish applications in a categorized catalog to be perused and deployed by application consumers. The selection of applications available within the catalog is intended to be that of released versions (ready-state) of applications (cloud-native or enterprise-architected), not application versions that are mid-development. Ideally, these are applications ready to be consumed and run by application users.
layout: post
guid: http://blog.gingergeek.com/?p=899
permalink: /2014/11/going-native-with-openstack-centric-applications-murano/
articleimg:
  - http://blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano.png
dsq_thread_id:
  - "4744160277"
image: /wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-tall.png
categories:
  - openstack
tags:
  - docker
  - glance
  - heat
  - mistral
  - murano
  - openstack
  - solum
---
Following on our previous discussion [surveying the projects supporting applications within OpenStack](http://blog.gingergeek.com/2014/11/going-native-with-openstack-centric-applications-overview/), let’s continue our review with an in-depth look at the OpenStack-native Application Catalog: Murano, currently an incubation status project, having seen its functionality and core services integration advanced over the past few OpenStack releases.

[<img class="alignleft" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano.png?w=150" alt="OpenStack Centric Applications - Murano"  data-recalc-dims="1" />](https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano.png)

### What is it?

An application catalog developed by Mirantis, HP and others (now including Cisco), that allows application developers and cloud administrators to publish applications in a categorized catalog to be perused and deployed by application consumers. The selection of applications available within the catalog is intended to be that of released versions (ready-state) of applications (cloud-native or enterprise-architected), not application versions that are mid-development. Ideally, these are applications ready to be consumed and run by application users.<!--more-->

### Functionality Highlights

  * <div id="attachment_883" style="width: 310px" class="wp-caption alignright">
      <a href="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Catalog-UI.png"><img class="wp-image-883 size-medium" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Catalog-UI.png?resize=300%2C207" alt="OpenStack Centric Applications - Murano Application Catalog UI" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Catalog-UI.png?resize=300%2C207 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Catalog-UI.png?resize=1024%2C708 1024w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Catalog-UI.png?w=1196 1196w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
      
      <p class="wp-caption-text">
        Murano Application Catalog UI
      </p>
    </div>Supports Windows and Linux applications

  * Leverages HOT templates for application definition
  * Controls Heat stack creation and updates processes
  * Track application properties and dependencies
  * Defines provisioning workflow definitions and executes them
  * Introduces “Application” and “Environment” constructs
  * Provides UI for application topology visualization
  * Control lifecycle of a deployed application
  * Allows simple management of access to an application
  * Compose an environment from multiple application components
  * Out of the Box Cataloged Applications 
      * 16 sample applications available now
      * 6 production-grade applications on Mirantis OpenStack Express**
  * Multiple application formats supported: 
      * HOT Templates
      * MuranoPL
  * Vision to support 
      * Other application model formats: 
          * Parallels APS format
          * TOSCA format
      * Pricing; billing system integration

### User Personas & Capabilities

As an application catalog, Murano, primarily focuses on three user personas, the _Cloud Administrator_, _Application Consumer_ and _Application Publisher_ receiving the most emphasis upfront in the development of this project.

#### Application Consumer

[<img class="alignleft size-thumbnail wp-image-889" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-User-Persona.png?resize=150%2C150" alt="OpenStack Centric Applications - User Persona" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-User-Persona.png?resize=150%2C150 150w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-User-Persona.png?resize=300%2C300 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-User-Persona.png?w=677 677w" sizes="(max-width: 150px) 100vw, 150px" data-recalc-dims="1" />](https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-User-Persona.png)The _Application Consumer_ selects and deploys instances of applications into environments they define. The _Application Consumer_ also…

  * …browses catalog (search, category, tags, etc)
  * …creates new environments
  * …deploys applications in environments
  * …monitors application statistics

#### Application Publisher

The _Application Publisher_ creates application definitions (packages) that are imported as entries into the application catalog for perusal by _Application Consumers_. The _Application Publisher_ also…

  * …defines application metadata (author, help message, version, etc)
  * …identifies cloud resource allocation (HOT templates)
  * …creates application deployment specifications (HOT templates)
  * …defines a template for dynamic visualization of application topology (Horizon)
  * …identifies metrics collection (Ceilometer)
  * …establishes actions & events (Murano & Mistral)
  * …imports and publishes application definition to catalog

#### Cloud Administrator

The _Cloud Administrator_ is responsible for running the application catalog and providing stable infrastructure upon which to deploy and run applications. The _Cloud Administrator_ also…

  * …curates application catalog (certification and signing of packages)
  * …configures access to applications
  * …defines billing rules*

### Application Packaging Process

Currently, Murano applications may be packaged using two different formats to describe the application – the

<div id="attachment_884" style="width: 310px" class="wp-caption alignleft">
  <a href="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Packaging.png"><img class="wp-image-884 size-medium" src="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Packaging.png?resize=300%2C155" alt="OpenStack Centric Applications - Murano Application Packaging" srcset="https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Packaging.png?resize=300%2C155 300w, https://i1.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Application-Packaging.png?resize=1024%2C529 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Murano Application Packaging Process
  </p>
</div>MuranoPL or a HOT template. There’s roadmap to support addition application description formats. While these two methodologies vary in terms of how the orchestration is performed during provisioning of an instance of the app, their are common attributes (catalog metadata) like an application display name, logo, description, author, tags. For those familiar with other domain-specific languages of other popular configuration management frameworks, the MuranoPL is of little challenge to pick up (you may lean into  use Bash or Powershell if more comfortable) or you may opt to use SoftwareConfig and SoftwareDeploy of HOT.

### Architectural Overview & Core Services Integration

See the “Murano Architectural Overview” diagram for a visual representation of how Murano is tightly integrated with core OpenStack services. It’s relationship to existing core services breaks down as follows:

<div id="attachment_885" style="width: 310px" class="wp-caption alignright">
  <a href="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Architectural-Overview.png"><img class="wp-image-885 size-medium" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Architectural-Overview.png?resize=300%2C140" alt="OpenStack Centric Applications - Murano Architectural Overview" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Architectural-Overview.png?resize=300%2C140 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Architectural-Overview.png?resize=1024%2C479 1024w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Architectural-Overview.png?w=2000 2000w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Murano Architectural Overview
  </p>
</div>

<div style="margin-left: .25in;">
  <h4>
    Glance
  </h4>
  
  <p>
    Originally designed as an image repository, Murano will use Glance to store & query application definitions. Glance is used as an artifact repository to store application definitions, query & search them and store images required by applications. Images used by Murano are marked with specific metadata, which is used by Murano to derive appropriate selections within the UI during application deployment time.
  </p>
  
  <h4>
    Heat
  </h4>
  
  <ul>
    <li>
      Cloud resource allocation specific to the application <ul>
        <li>
          Resources required by application is allocated using Heat
        </li>
      </ul>
    </li>
    
    <li>
      Application provisioning / deployment via Heat Software Configuration
    </li>
    <li>
      Life-cycle callbacks*
    </li>
  </ul>
  
  <h4>
    Horizon
  </h4>
  
  <p>
    Horizon is used to provide the Application Catalog user interface wherein <em>Application Publishers </em>may browse and deploy applications. Horizon is also u<span style="line-height: 1.5em;">sed to both build applications and visualize the topology provisioned applications. The need for this type of dynamic user interface (application topology canvas) has been p</span><span style="line-height: 1.5em;">roposed as separate project to provide common support to other Application-oriented projects – Heat, Solum, Mistral and Murano. This application blueprint designer project is codename – </span><a style="font-style: italic;" href="https://wiki.openstack.org/wiki/Merlin" target="_blank">Merlin</a>.
  </p>
  
  <h4>
    Docker
  </h4>
  
  <p>
    Murano supports existing Nova and Heat plugins. See the “Murano and Containers” section below.
  </p>
  
  <h4>
    Ceilometer
  </h4>
  
  <p>
    Murano uses Ceilometer for application metric collection & processing. Additionally, Ceilometer events may be subscribed to and trigger specific actions (see below) for autoscaling, HA, DR and other.
  </p>
  
  <h4>
    Mistral
  </h4>
  
  <ul>
    <li>
      Workflows are used when complex workflow outside of Heat is needed.
    </li>
    <li>
      Actions (also available w/o Mistral) <ul>
        <li>
          Application level ad-hoc actions (e.g. create backup, enable/disable some feature, or create user for an application) will also be defined in Mistral.
        </li>
        <li>
          Events (e.g. when X occurs then do Y)
        </li>
        <li>
          Events mapping to actions
        </li>
      </ul>
    </li>
  </ul>
</div>

<div id="attachment_882" style="width: 310px" class="wp-caption alignleft">
  <a href="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Actions.png"><img class="wp-image-882 size-medium" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Actions.png?resize=300%2C202" alt="OpenStack Centric Applications - Murano Actions" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Actions.png?resize=300%2C202 300w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-Actions.png?w=995 995w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Murano Actions – application-specific scaling
  </p>
</div>

### Actions & Events

<div>
  Classic runbook automation applies here – Murano allows the <em>Application Publisher</em> to define various custom actions to be taken upon trigger by an interesting event. What constitutes and interesting event is up to the <em>Application Publisher</em>, who may define any action in the application definition and associate the action to a specific workflow. By exposing a webhook to trigger the action (and workflow), they may be triggered by Ceilometer alarms or any 3rd party tool.
</div>

<div>
</div>

<div>
  Common use cases are auto-scaling, HA and DR. The “Murano Actions” diagram shows an example of an autoscaling scenario in which an application might require additional database instance based web server load.
</div>

### Murano and Containers

Murano inherently supports Docker containers by relying upon existing OpenStack components for container integration and orchestration. This means that there are no considerations to be accounted for within the MuranoPL to describe the application package to support containers. Similarly, when using Heat templates at the core of the application package, only reference to Docker resources and images is needed to support container orchestration by Heat. There are different ways of using Docker in OpenStack via Murano:

<p style="padding-left: 15px;">
  1) Heat template can use Heat::Docker
</p>

<ul style="margin-left: 15px;">
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">Heat::Docker driver leverages Heat engine directly to instantiate containers</span>
  </li>
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">Use Heat when Nova does not support Docker</span>
  </li>
</ul>

<p style="margin-left: 15px;">
  2) Heat template can use Nova::Docker
</p>

<ul style="margin-left: 15px;">
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">Use when you have a bare metal Docker installation</span>
  </li>
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">Through Nova API, create a container without a VM being created to host</span>
  </li>
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">Nova can go to bare metale to create Docker container</span>
  </li>
  <li style="padding-left: 15px;">
    <span style="line-height: 1em;">User provides Heat template, workflow (Murano DSL) and image</span>
  </li>
</ul>

<p style="padding-left: 15px;">
  3) Not recommended – Use Heat resource to create a VM with Docker inside and boot an image file to the VM with <code>docker run</code>.
</p>

The Murano team is looking to add autoscaling for Docker services, facilitate Docker application placement and integration with monitoring and network services.

### Murano as a Southbound Catalog

[<img class="alignleft wp-image-930" src="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-tall.png?resize=165%2C200" alt="OpenStack Centric Applications - Murano" srcset="https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-tall.png?resize=246%2C300 246w, https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-tall.png?w=445 445w" sizes="(max-width: 165px) 100vw, 165px" data-recalc-dims="1" />](https://i0.wp.com/blog.gingergeek.com/wp-content/uploads/2014/11/OpenStack-Centric-Applications-Murano-tall.png)Murano has two different northbound APIs to expose access to applications in the catalog – REST and AMQP (Services Broker). Within the Juno release, the Services Broker has only been prototyped. It’s scheduled to be fully-implemented in Kilo. While other use cases may exist, the primary use case for these northbound API revolves around allowing northbound catalogs to access and expose OpenStack-native applications.

The _Services Broker_ supports CRUD and binds service with your application. A proof of concept has been completed to integrate Cloud Foundry with Murano via the Service Broker. When CloudFoundry is integrated to Murano, CloudFoundry users see and order Murano applications in CloudFoundry.

Using the _REST API_, Murano may be integrated as a southbound application catalog to expose OpenStack-native applications as SaaS application profiles available for users of a northbound catalog. Users benefit from existing services offered on top of OpenStack. This enables application components to be split across infrastructure (having application components deployed into different infrastructures).

### Kilo Roadmap

While subject to change, based on Kilo design summit discussions this week, the project team aims to bite off the following capabilities before the next release in May.

  * Implementing CloudFoundry ServiceBroker API
  * Use of Glance as an artifact repository
  * Support pluggable package definitions formats: 
      * TOSCA (Topology and Orchestration Specification for Cloud Applications)
      * APS (Parallels Application Standard)
  * Multiple Heat Stacks and OpenStack Cloud support 
      * Availability Zones (for DR)
      * Multiple OpenStack clouds
  * Pluggable Architecture 
      * Integration with 3rd party API (F5, Brocade etc.)
      * Package format plugins

We’ll continue our review of support for applications within OpenStack in the next post of this series by diving into application lifecycle management with Solum.

<small>—<br /> *Future capability<br /> **To be released in November 2014 on Mirantis OpenStack Express<br /> Murano logo and screenshots reprinted with permission from Mirantis Inc.</small>