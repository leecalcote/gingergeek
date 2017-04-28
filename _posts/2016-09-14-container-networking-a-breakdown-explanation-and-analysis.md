---
id: 1573
title: 'Container Networking: A Breakdown, Explanation and Analysis'
date: 2016-09-14T12:36:24+00:00
author: Lee
excerpt: 'While many gravitate toward network overlays as a popular approach to addressing container networking across hosts, the functions and types of container networking vary greatly and are worth better understanding as you consider the right type for your environment. '
layout: post
guid: http://blog.gingergeek.com/?p=1573
permalink: /2016/09/container-networking-a-breakdown-explanation-and-analysis/
dsq_thread_id:
  - "5244202506"
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
[<img data-id="1577"  src="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/09/container-rope.jpg?resize=300%2C169" alt="container-rope" class="alignleft size-medium wp-image-1577" srcset="https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/09/container-rope.jpg?resize=300%2C169 300w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/09/container-rope.jpg?resize=768%2C432 768w, https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/09/container-rope.jpg?w=960 960w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />](https://i2.wp.com/blog.gingergeek.com/wp-content/uploads/2016/09/container-rope.jpg)

<p style="text-align: right;">
  <em>Originally published on <a href="http://thenewstack.io/container-networking-breakdown-explanation-analysis/">The New Stack</a> on Sept. 4th, 2016.</em>
</p>

While many gravitate toward network overlays as a popular approach to addressing container networking across hosts, the functions and types of container networking vary greatly and are worth better understanding as you consider the right type for your environment. Some types are container engine-agnostic, and others are locked into a specific vendor or engine. Some focus on simplicity, while others on breadth of functionality or on being IPv6-friendly and multicast-capable. Which one is right for you depends on your application needs, performance requirements, workload placement (private or public cloud), etc. Let’s review the more commonly available types of container networking.

There are various ways in which container-to-container and container-to-host connectivity are provided. This article focuses primarily on a breakdown of current container networking types, including:

  * None
  * Bridge
  * Overlay
  * Underlay

<!--more-->

## Antiquated Types of Container Networking

The approach to networking has evolved as container technology advances. Two modes of networking have come and all but disappeared already.

### Links and Ambassadors

Prior to having multi-host networking support and orchestration with Swarm, Docker began with single-host networking, facilitating network connectivity via links as a mechanism for allowing containers to discover each other via environment variables or /etc/hosts file entries, and transfer information between containers. The links capability was commonly combined with the [ambassador pattern](https://docs.docker.com/engine/admin/ambassador_pattern_linking/) to facilitate linking containers across hosts and reduce the brittleness of hard-coded links. The biggest issue with this approach was that it was too static. Once a container was created and the environment variables defined, if the related containers or services moved to new IP addresses, then it was impossible to change the values of those variables.

### Container-Mapped Networking

In this mode of networking, one container reuses (maps to) the networking namespace of another container. This mode of networking may only be invoked when running a Docker container like this: –net:container:_some\_container\_name\_or\_id_.

This run command flag tells Docker to put this container’s processes inside of the network stack that has already been created inside of another container. While sharing the same IP and MAC address and port numbers as the first container, the new container’s processes are still confined to its own filesystem, process list and resource limits. Processes on the two containers will be able to connect to each other over the loopback interface.

This style of networking is useful for performing diagnostics on a running container and the container is missing the necessary diagnostic tools (e.g., curl or dig). A temporary container with the necessary diagnostics tools may be created and attached to the first container’s network.

Container-mapped networking may be used to emulate pod-style networking, in which multiple containers share the same network namespace. Benefits, such as sharing localhost communication and sharing the same IP address, are inherent to the notion that containers run in the same pod, which is the behavior of rkt containers.

## Current Types of Container Networking

Lines of delineation of networking revolve around IP-per-container versus IP-per-pod models and the requirement of network address translation (NAT) versus no translation needed.

### None

None is straightforward in that the container receives a network stack, but lacks an external network interface. It does, however, receive a loopback interface. Both the rkt and Docker container projects provide similar behavior when none or null networking is used. This mode of container networking has a number of uses including testing containers, staging a container for a later network connection, and being assigned to containers with no need for external communication.

### Bridge

A Linux bridge provides a host internal network in which containers on the same host may communicate, but the IP addresses assigned to each container are not accessible from outside the host. Bridge networking leverages iptables for NAT and port-mapping, which provide single-host networking. Bridge networking is the default Docker network type (i.e., docker0), where one end of a virtual network interface pair is connected between the bridge and the container.

Here’s an example of the creation flow:

  1. A bridge is provisioned on the host.
  2. A namespace for each container is provisioned inside that bridge.
  3. Containers’ ethX are mapped to private bridge interfaces.
  4. iptables with NAT are used to map between each private container and the host’s public interface.

NAT is used to provide communication beyond the host. While bridged networks solve port-conflict problems and provide network isolation to containers running on one host, there’s a performance cost related to using NAT.

### Host

In this approach, a newly created container shares its network namespace with the host, providing higher performance — near metal speed — and eliminating the need for NAT; however, it does suffer port conflicts. While the container has access to all of the host’s network interfaces, unless deployed in privilege mode, the container may not reconfigure the host’s network stack.

Host networking is the default type used within Mesos. In other words, if the framework does not specify a network type, a new network namespace will not be associated with the container, but with the host network. Sometimes referred to as native networking, host networking is conceptually simple, making it easier to understand, troubleshoot and use.

### Overlay

Overlays use networking tunnels to deliver communication across hosts. This allows containers to behave as if they are on the same machine by tunneling network subnets from one host to the next; in essence, spanning one network across multiple hosts. Many tunneling technologies exist, such as virtual extensible local area network (VXLAN).

VXLAN has been the tunneling technology of choice for Docker libnetwork, whose multi-host networking entered as a native capability in the 1.9 release. With the introduction of this capability, Docker chose to leverage HashiCorp’s Serf as the gossip protocol, selected for its efficiency in neighbor table exchange and convergence times.

For those needing support for other tunneling technologies, Flannel may be the way to go. It supports udp, vxlan, host-gw, aws-vpc or gce. Each of the cloud provider tunnel types creates routes in the provider’s routing tables, just for your account or virtual private cloud (VPC). The support for public clouds is particularly key for overlay drivers given that among others, overlays best address hybrid cloud use cases and provide scaling and redundancy without having to open public ports.

Multi-host networking requires additional parameters when launching the Docker daemon, as well as a key-value store. Some overlays rely on a distributed key-value store. If you’re doing container orchestration, you’ll already have a distributed key-value store lying around.

Overlays focus on the cross-host communication challenge. Containers on the same host that are connected to two different overlay networks are not able to communicate with each other via the local bridge — they are segmented from one another.

### Underlays

Underlay network drivers expose host interfaces (i.e., the physical network interface at eth0) directly to containers or VMs running on the host. Two such underlay drivers are media access control virtual local area network (MACvlan) and internet protocol VLAN (IPvlan). The operation of and the behavior of MACvlan and IPvlan drivers are very familiar to network engineers. Both network drivers are conceptually simpler than bridge networking, remove the need for port-mapping and are more efficient. Moreover, IPvlan has an L3 mode that resonates well with many network engineers. Given the restrictions — or lack of capabilities — in most public clouds, underlays are particularly useful when you have on-premises workloads, security concerns, traffic priorities or compliance to deal with, making them ideal for brownfield use. Instead of needing one bridge per VLAN, underlay networking allows for one VLAN per subinterface.

#### MACvlan

MACvlan allows the creation of multiple virtual network interfaces behind the host’s single physical interface. Each virtual interface has unique MAC and IP addresses assigned, with a restriction: the IP addresses need to be in the same broadcast domain as the physical interface. While many network engineers may be more familiar with the term subinterface (not to be confused with a secondary interface), the parlance used to describe MACvlan virtual interfaces is typically upper or lower interface. MACvlan networking is a way of eliminating the need for the Linux bridge, NAT and port-mapping, allowing you to connect directly to the physical interface.

MACvlan uses a unique MAC address per container, and this may cause an issue with network switches that have security policies in place to prevent MAC spoofing, by allowing only one MAC address per physical switch interface.

Container traffic is filtered from being able to speak to the underlying host, which completely isolates the host from the containers it runs. The host cannot reach the containers. The container is isolated from the host. This is useful for service providers or multitenant scenarios and has more isolation than the bridge model.

Promiscuous mode is required for MACvlan; MACvlan has four modes of operation, with only the bridge mode supported in Docker 1.12. MACvlan bridge mode and IPvlan L2 mode are just about functionally equivalent. Both modes allow broadcast and multicast traffic ingress. These underlay protocols were designed with on-premises use cases in mind. Your public cloud mileage will vary as most do not support promiscuous mode on their VM interfaces.

A word of caution: MACvlan bridge mode assigning a unique MAC address per container can be a blessing in terms of tracing network traffic and end-to-end visibility; however, with a typical network interface card (NIC), e.g., Broadcom, having a ceiling of 512 unique MAC addresses, this upper limit should be considered.

#### IPvlan

IPvlan is similar to MACvlan in that it creates new virtual network interfaces and assigns each a unique IP address. The difference is that the same MAC address is used for all pods and containers on a host — the same MAC address of the physical interface. The need for this behavior is primarily driven by the fact that a commonly configured security posture of many switches is to shut down switch ports with traffic sourced from more than one MAC address.

Best run on kernels 4.2 or newer, IPvlan may operate in either L2 or L3 modes. Like MACvlan, IPvlan L2 mode requires that IP addresses assigned to subinterfaces be in the same subnet as the physical interface. IPvlan L3 mode, however, requires that container networks and IP addresses be on a different subnet than the parent physical interface.

802.1q configuration on Linux hosts, when created using IP Link, is ephemeral, so most operators use network startup scripts to persist configuration. With container engines running underlay drivers and exposing APIs for programmatic configuration of VLANs, automation stands to improve. For example, when new VLANs are created on a top of rack switch, these VLANs may be pushed into Linux hosts via the exposed container engine API.ico

#### MACvlan and IPvlan

When choosing between these two underlay types, consider whether or not you need the network to be able to see the MAC address of the individual container.

With respect to the address resolution protocol (ARP) and broadcast traffic, the L2 modes of both underlay drivers operate just as a server connected to a switch does, by flooding and learning using 802.1d packets. In IPvlan L3 mode, however, the networking stack is handled within the container. No multicast or broadcast traffic is allowed in. In this sense, IPvlan L3 mode operates as you would expect an L3 router to behave.

Note that upstream L3 routers need to be made aware of networks created using IPvlan. Network advertisement and redistribution into the network still needs to be done. Today, Docker is experimenting with Border Gateway Protocol (BGP). While static routes can be created on top of the rack switch, projects like [goBGP](http://osrg.github.io/gobgp/) have sprouted up as a container ecosystem-friendly way to provide neighbor peering and route exchange functionality.

Although multiple modes of networking are supported on a given host, MACvlan and IPvlan can’t be used on the same physical interface concurrently. In short, if you’re used to running trunks down to hosts, L2 mode is for you. If scale is a primary concern, L3 has the potential for massive scale.

#### Direct Routing

For the same reasons that IPvlan L3 mode resonates with network engineers, they may choose to push past L2 challenges and focus on addressing network complexity in Layer 3 instead. This approach benefits from the leveraging of existing network infrastructure to manage the container networking. The container networking solutions focused at L3 use routing protocols to provide connectivity, which is arguably easier to interoperate with existing data center infrastructure, connecting containers, VMs and bare metal servers. Moreover, L3 networking scales and affords granular control, in terms of filtering and isolating network traffic.

[Calico](https://www.projectcalico.org) is one such project and uses BGP to distribute routes for every network —  specifically to that workload using a /32 — which allows it to seamlessly integrate with existing data center infrastructure without the need for overlays. Without the overhead of overlays or encapsulation, the result is networking with exceptional performance and scale. Routable IP addresses for containers expose the IP address to the rest of the world; hence, ports are inherently exposed to the outside world. Network engineers trained and accustomed to deploying, diagnosing and operating networks using routing protocols may find direct routing easier to digest. However, it’s worth noting that Calico doesn’t support overlapping IP addresses.

#### Fan Networking

Fan networking is a way of gaining access to many more IP addresses, expanding from one assigned IP address to 250 IP addresses. This is a performant way of getting more IPs without the need for overlay networks. This style of networking is particularly useful when running containers in a public cloud, where a single IP address is assigned to a host and spinning up additional networks is prohibitive, or running another load-balancer instance is costly.

#### Point-to-Point

Point-to-point is perhaps the simplest type of networking and the default networking used by CoreOS rkt. Using NAT, or IP Masquerade (IPMASQ), by default, it creates a virtual ethernet pair, placing one on the host and the other in the container pod. Point-to-point networking leverages iptables to provide port-forwarding not only for inbound traffic to the pod but also for internal communication between other containers in the pod over the loopback interface.

## Capabilities

Outside of pure connectivity, support for other networking capabilities and network services needs to be considered. Many modes of container networking either leverage NAT and port-forwarding or intentionally avoid their use. IP address management (IPAM), multicast, broadcast, IPv6, load-balancing, service discovery, policy, quality of service, advanced filtering and performance are all additional considerations when selecting networking.

The question is whether these capabilities are supported and how developers and operators are empowered by them. Even if a container networking capability is supported by your runtime, orchestrator or plugin of choice, it may not be supported by your infrastructure. While some tier 2 public cloud providers offer support for IPv6, the lack of support for IPv6 in top public clouds reinforces the need for other networking types, such as overlays and fan networking.

In terms of IPAM, to promote ease of use, most container runtime engines default to host-local for assigning addresses to containers, as they are connected to networks. Host-local IPAM involves defining a fixed block of IP addresses to be selected. Dynamic Host Configuration Protocol (DHCP) is universally supported across container networking projects. Container Network Model (CNM) and Container Network Interface (CNI) both have IPAM built-in and plugin frameworks for integration with IPAM systems — a key capability to adoption in many existing environments.