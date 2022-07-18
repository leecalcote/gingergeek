---
id: 1074
title: 22 new concerns added to Docker security benchmark
date: 2016-04-15T08:43:12+00:00
author: Lee
excerpt: 'Collaborators working under governance of the Center for Internet Security released the second version of the Docker Security Benchmark in conjunction with the Docker 1.11.0 release. '
layout: post
guid: http://gingergeek.com/?p=1074
permalink: /2016/04/22-new-concerns-added-to-docker-security-benchmark/
dsq_thread_id:
  - "4749345013"
image: /wp-content/uploads/2016/04/CIS-Docker-Benchmark.png
categories:
  - containers
  - systems management
tags:
  - containers
  - docker
  - security
---
<img class="size-medium wp-image-1075 align left" src="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/04/CIS-Docker-Benchmark.png?resize=300%2C225" alt="CIS-Docker-Benchmark" srcset="https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/04/CIS-Docker-Benchmark.png?resize=300%2C225 300w, https://i0.wp.com/gingergeek.com/wp-content/uploads/2016/04/CIS-Docker-Benchmark.png?w=620 620w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /><small><em>Article originally appeared on <a href="http://www.networkworld.com/article/3056031/open-source-tools/22-new-concerns-added-to-docker-security-benchmark.html">Network World</a> on April 15th, 2016.</em></small>

Security has and continues to be an impediment to container adoption. Whether containers are less or more secure than their virtual machine counterparts is a topic of continued debate.

Like any debate, there are merits to arguments on both sides with a bit of FUD interlaced. Many efforts have been undertaken within the container ecosystem to educate adopters and improve their comprehension of available tooling and security postures within platforms and offerings—be that in the form of static analysis (image scanning), runtime vulnerability detection, provenance (image signing), fine-grained authorization, cryptographic verification, etc.
  
<!--more-->


  
The breadth of need for improved security capabilities has provided an opportunity for emerging start-ups to focus specifically on the container security space and others to dedicate their company’s mission to securing the Internet. Having spent time with most of the vendors in this space, I’ll say that as you might expect, it’s a quickly changing landscape. One thing is evident: open source communities and vendors at every layer—from hardware through operating system, container runtime, container image, host to cluster orchestrator, PaaS to CaaS—have significantly marshalled forward security-centered improvements in the past year.

The <a href="https://www.cisecurity.org/" target="new">Center for Internet Security</a> (CIS) is one of those organizations. CIS is dedicated to enhancing cybersecurity readiness and response between both public and private sectors. CIS produces Security Benchmarks as a way of providing defined, unbiased and consensus-based industry best practices to help organizations assess and improve their security. Thanks to a community of collaborators (_disclaimer: I am a member of the CIS Docker Benchmarks working group_), the first CIS Docker Benchmark was published last April for Docker 1.6. A year later (April 13, 2016), a revision of this benchmark was released in concert with the Docker 1.11.0 release.

<div class="apart ad lazyload_ad_article">
</div><aside id="" class="nativo-promo smartphone"></aside> 

Each CIS Docker Benchmark provides prescriptive guidance (in the form of rules) for establishing a secure configuration posture for Docker container infrastructure. The new benchmark version has been published with 22 new rules added and 23 rules removed, netting 83 rules in total.

As Docker has evolved over the past year, several rules have been updated or simply removed, as these concerns are now addressed in later versions of Docker tooling. Other updates in the rules are simply a reflection of architectural shifts Docker has made. In the 1.11.0 release, Docker has separated the concern of supervising containers and their runtime, splitting into two daemons: <a href="https://containerd.tools/" target="new">containerd and runc</a>.

The benchmark categorizes Docker security concerns into these groups (with number of concerns in parenthesis):

  * Host Configuration (15)
  * Docker daemon configuration (13)
  * Docker daemon configuration files (20)
  * Container Images and Build File (5)
  * Container Runtime (25)
  * Docker Security Operations (5)

Each rule not only describes the security concern and how to perform an audit to ascertain your deployment’s disposition, but also suggests how you may remediate the concern. Both rules and their remediations are written from the perspective of a container host, not a cluster, so how you choose to remediate the concern will vary based on your cluster size and platform choice (bare metal, container PaaS, cloud, etc.)

New rules introduced in the <a href="https://benchmarks.cisecurity.org/tools2/docker/CIS_Docker_1.11.0_Benchmark_v1.0.0.pdf" target="new">CIS Docker 1.11.0 Benchmark</a> (pdf):

  * Host Configuration 
      * 1.11 Audit Docker files and directories – docker.socket
      * 1.13 Audit Docker files and directories – /etc/docker/daemon.json
      * 1.14 Audit Docker files and directories – /usr/bin/docker-containerd
      * 1.15 Audit Docker files and directories – /usr/bin/docker-runc
  * Docker Daemon Configuration 
      * 2.8 Enable user namespace support
      * 2.9 Confirm default cgroup usage
      * 2.10 Do not change base device size until needed
      * 2.11 Use authorization plugin
      * 2.12 Configure centralized and remote logging
      * 2.13 Disable operations on legacy registry (v1)
  * Docker Daemon Configuration Files 
      * 3.17 Verify that daemon.json file ownership is set to root:root
      * 3.18 Verify that daemon.json file permissions are set to 644 or more restrictive
      * 3.19 Verify that /etc/default/docker file ownership is set to root:root
      * 3.20 Verify that /etc/default/docker file permissions are set to 644 or more restrictive
  * Container Images and Build File 
      * 4.5 Enable Content trust for Docker
  * Container Runtime 
      * 5.19 Do not set mount propagation mode to shared
      * 5.20 Do not share the host’s UTS namespace
      * 5.21 Do not disable default seccomp profile
      * 5.22 Do not docker exec commands with privileged option
      * 5.23 Do not docker exec commands with user option
      * 5.24 Confirm cgroup usage
      * 5.25 Restrict container from acquiring additional privileges

Some container security vendors participate in the creation of the Docker Security Benchmark, while many others incorporate detection of these issues into their offering or project. While some include policy-driven orchestration to address failed security tests, few actually fully remediate the issue (only some issues are well-suited for automated remediation).

Security Configuration Benchmarks are distributed free of charge to propagate their worldwide use and adoption as user-originated standards. One such tool adopting the 1.11.0 benchmark concerns is the <a href="https://github.com/docker/docker-bench-security" target="new">Docker Bench for Security</a>—an open source, command-line tool used to perform checks in accordance with the CIS Docker Benchmark.