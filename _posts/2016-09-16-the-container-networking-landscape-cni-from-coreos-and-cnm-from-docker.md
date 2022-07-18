---
id: 1581
title: 'The Container Networking Landscape: CNI from CoreOS and CNM from Docker'
date: 2016-09-16T12:48:03+00:00
author: Lee
excerpt: 'There are two proposed standards for configuring network interfaces for Linux containers: the container network model (CNM) and the container network interface (CNI). Networking is complex, and there are many ways to deliver functionality. Arguments can be made as to which one is easier to adopt than the next, or which one is less tethered to their benefactor’s technology.'
layout: post
guid: http://gingergeek.com/?p=1581
permalink: /2016/09/the-container-networking-landscape-cni-from-coreos-and-cnm-from-docker/
dsq_thread_id:
  - "5244190701"
categories:
  - containers
  - network management
tags:
  - containers
  - docker
  - kubernetes
  - marathon
  - mesos
  - networking
  - swarm
---
[<img data-id="1582"  src="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/10/glen-canyon.jpg?resize=300%2C224" alt="glen-canyon" class="alignleft size-medium wp-image-1582" srcset="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/10/glen-canyon.jpg?resize=300%2C224 300w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/10/glen-canyon.jpg?resize=768%2C574 768w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/10/glen-canyon.jpg?w=960 960w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/10/glen-canyon.jpg)

<p style="text-align: right;">
  <em>Originally published on <a href="http://thenewstack.io/container-networking-landscape-cni-coreos-cnm-docker/">The New Stack</a> on Sept. 4th, 2016.</em>
</p>

There are two proposed standards for configuring network interfaces for Linux containers: the container network model (CNM) and the container network interface (CNI). Networking is complex, and there are many ways to deliver functionality. Arguments can be made as to which one is easier to adopt than the next, or which one is less tethered to their benefactor’s technology.

When evaluating any technology, some important considerations are community adoption and support. Some perspectives have been formed on which model has a lower barrier to entry. Finding the right metrics to determine the velocity of a project is tricky. Plugin vendors also need to consider the relative ease by which plugins may be written for either of these two models.<!--more-->

## Container Network Model

The [Container Network Model](https://github.com/docker/libnetwork/blob/master/docs/design.md) (CNM) is a specification proposed by Docker, adopted by projects such as [libnetwork](https://github.com/docker/libnetwork/blob/master/docs/design.md), with integrations from projects and companies such as [Cisco Contiv](http://contiv.github.io/), [Kuryr](https://wiki.openstack.org/wiki/Kuryr), Open Virtual Networking (OVN), [Project Calico](https://www.projectcalico.org), [VMware](https://github.com/vmware/docker-volume-vsphere) and [Weave](https://github.com/weaveworks/weave).

<div id="attachment_1587" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png"><img data-id="1587"  src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png?resize=300%2C200" alt=" Figure 1: Libnetwork provides an interface between the Docker daemon and network drivers." class="size-medium wp-image-1587" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png?resize=300%2C200 300w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png?resize=768%2C512 768w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png?resize=1024%2C683 1024w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Drivers.png?w=1600 1600w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Figure 1: Libnetwork provides an interface between the Docker daemon and network drivers.
  </p>
</div>

Libnetwork is the canonical implementation of the CNM specification. Libnetwork provides an interface between the Docker daemon and network drivers. The network controller is responsible for pairing a driver to a network. Each driver is responsible for managing the network it owns, including services provided to that network like IPAM. With one driver per network, multiple drivers can be used concurrently with containers connected to multiple networks. Drivers are defined as being either native (built-in to libnetwork or Docker supported) or remote (third party plugins). The native drivers are none, bridge, overlay and MACvlan. Remote drivers may bring any number of capabilities. Drivers are also defined as having a local scope (single host) or global scope (multi-host).

<div id="attachment_1586" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png"><img data-id="1586"  src="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png?resize=300%2C200" alt="Figure 2: Containers being connected through a series of network endpoints." class="size-medium wp-image-1586" srcset="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png?resize=300%2C200 300w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png?resize=768%2C512 768w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png?resize=1024%2C683 1024w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Model-Interfacing.png?w=1600 1600w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Figure 2: Containers being connected through a series of network endpoints.
  </p>
</div>

  * **Network Sandbox:** Essentially the networking stack within a container, it is an isolated environment to contain a container’s network configuration.
  * **Endpoint:** A network interface that typically comes in pairs. One end of the pair sits in the network sandbox, while the other sits in a designated network. Endpoints join exactly one network, and multiple endpoints can exist within a single network sandbox.
  * **Network**: A group of endpoints. A network is a uniquely identifiable group of endpoints that can communicate with each other.

A final, flexible set of CNM constructs are **options** and **labels** (key-value pairs of metadata). CNM supports the notion of user-defined **labels** (defined using the — label flag), which are passed as metadata between libnetwork and drivers. Labels are powerful in that the runtime may inform driver behavior.

## Container Network Interface

The [Container Network Interface](https://github.com/containernetworking/cni) (CNI) is a container networking specification proposed by CoreOS and adopted by projects such as [Apache Mesos](https://github.com/apache/mesos/blob/master/docs/cni.md), [Cloud Foundry](https://github.com/cloudfoundry-incubator/guardian-cni-adapter), [Kubernetes](http://kubernetes.io/docs/admin/network-plugins/)[,](https://github.com/cloudfoundry-incubator/guardian-cni-adapter) [Kurma](http://kurma.io/) and [rkt](https://coreos.com/blog/rkt-cni-networking.html). There are also plugins created by projects such as [Contiv Networking](https://github.com/contiv/netplugin), [Project Calico](https://github.com/projectcalico/calico-cni) [and](https://github.com/contiv/netplugin) [Weave](https://github.com/weaveworks/weave).

<div id="attachment_1589" style="width: 310px" class="wp-caption aligncenter">
  <a href="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png"><img data-id="1589"  src="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png?resize=300%2C200" alt="Figure 3: CNI is a minimal specification for adding and removing containers to networks." class="size-medium wp-image-1589" srcset="https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png?resize=300%2C200 300w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png?resize=768%2C512 768w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png?resize=1024%2C683 1024w, https://i1.wp.com/gingergeek.com/wp-content/uploads/2016/09/Chart_Container-Network-Interface-Drivers.png?w=1600 1600w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Figure 3: CNI is a minimal specification for adding and removing containers to networks.
  </p>
</div>

CNI was created as a minimal specification, built alongside a number of network vendor engineers to be a simple contract between the container runtime and network plugins. A JSON schema defines the expected input and output from CNI network plugins.

Multiple plugins may be run at one time with a container joining networks driven by different plugins. Networks are described in configuration files, in JSON format, and instantiated as new namespaces when CNI plugins are invoked. CNI plugins support two commands to add and remove container network interfaces to and from networks. Add gets invoked by the container runtime when it creates a container. Delete gets invoked by the container runtime when it tears down a container instance.

### CNI Flow

The container runtime needs to first allocate a network namespace to the container and assign it a container ID, then pass along a number of parameters (CNI config) to the network driver. The network driver then attaches the container to a network and reports the assigned IP address back to the container runtime via JSON.

Mesos is the latest project to add CNI support, and there is a Cloud Foundry implementation in progress. The current state of Mesos networking uses host networking, wherein the container shares the same IP address as the host. Mesos is looking to provide each container with its own network namespace, and consequently, its own IP address. The project is moving to an IP-per-container model and, in doing so, seeks to democratize networking such that operators have freedom to choose the style of networking that best suits their purpose.

Currently, CNI primitives handle concerns with IPAM, L2 and L3, and expect the container runtime to handle port-mapping (L4). From a Mesos perspective, this minimalist approach comes with a couple of caveats, one of these being that the CNI specification does not specify any port-mapping rules to be used for a container; this capability may be handled by the container runtime. A second caveat is the fact that while operators should be allowed to change the CNI configuration, the behavior of container operation when CNI configuration is modified is not accounted for in the specification. Mesos is addressing this ambiguity by ensuring that, upon restart of the CNI agent, they will checkpoint the CNI config when it is associated with the particular instance of the container.

## CNI and CNM

In many respects, these two container networking specifications democratize the selection of which type of container networking may be used, in that both are driver-based models, or plugin-based, for creating and managing network stacks for containers. Each allows multiple network drivers to be active and used concurrently, in that each provides a one-to-one mapping of the network to that network’s driver. Both models allow containers to join one or more networks. And each allows the container runtime to launch the network in its own namespace, segregating the application/business logic of connecting the container to the network to the network driver.

This modular driver approach is arguably more attractive to network operators than to application developers, in that operators are afforded the flexibility to select one or more drivers that deliver on their specific needs and fit into their existing mode of operation. Operators bear responsibility for ensuring service-level agreements (SLAs) are met, and security policies are enforced.

Both models provide separate extension points, aka plugin interfaces, for network drivers — to create, configure and connect networks — and IPAM — to configure, discover, and manage IP addresses. One extension point per function encourages composability.

CNM does not provide network drivers access to the container’s network namespace. The benefit here is that libnetwork acts as a broker for conflict resolution. An example conflict being when two independent network drivers provide the same static route, using the same route prefix, but point to different next-hop IP addresses. CNI does provide drivers with access to the container network namespace. CNI is considering how it might [approach arbitration](https://github.com/containernetworking/cni/issues/147) in such conflict resolution scenarios.

CNI supports integration with third-party IPAM and can be used with any container runtime. CNM is designed to support the Docker runtime engine only. With CNI’s simplistic approach, it’s been argued that it’s comparatively easier to create a CNI plugin than a CNM plugin.

These models promote modularity, composability and choice by fostering an ecosystem of innovation by third-party vendors who deliver advanced networking capabilities. The orchestration of network micro-segmentation can become simple API calls to attach, detach and swap networks. Interface containers can belong to multiple networks, and each container can publish different services in different networks. The idea of different network constructs as first-class citizens is reflected in the ability to detach a network service from an old container and attach it to a new container.

## Summary

As vendors and projects continue to evolve, the networking landscape continues to shift. Some offerings have consolidated or combined, such as Docker’s acquisition of SocketPlane, and the transition of Flannel to [Tigera](http://thenewstack.io/project-calico-flannel-join-forces-policy-secured-networking/) — a new startup that has [formed around Canal](http://thenewstack.io/project-calico-flannel-join-forces-policy-secured-networking/). Canal is a portmanteau of Calico and Flannel and a combination of those two projects. CoreOS will provide ongoing support for Flannel as an individual project, and will be integrating Canal with Tectonic, their enterprise solution for Kubernetes. Other changes come in the form of new project releases. Docker 1.12’s release of networking features, including underlay and load-balancing support, is no small step forward for the project.

While there’s a large number of container networking technologies and distinctly unique ways of approaching them, we’re fortunate in that much of the container ecosystem seems to have converged and built support around only two networking models, at least for now. Developers would like to eliminate manual network provisioning in containerized environments, and barring those who have misconceptions of their job insecurity, network engineers are ready for the same.

Like other resources, an intermediary step to automated provisioning is pre-provisioning, meaning network engineers would preallocate networks with assigned characteristics and services, such as, IP address space, IPAM, routing, QoS, etc., and developers or deployment engineers would identify and select from a pool of available networks in which to deploy their applications. Pre-provisioning needs to become a thing of the past, as we’re all ready to move on to automated provisioning.