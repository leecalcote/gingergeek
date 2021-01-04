---
id: 1796
title: How to customize an Istio Service Mesh
date: 2018-05-09T013:20:15+00:00
author: Lee
excerpt: Working with Istio? Learn how to customize it to mesh along with your architectural needs.
layout: post
guid: http://blog.gingergeek.com/?p=1796
permalink: /2018/05/how-to-customize-an-istio-service-mesh/
categories:
  - cncf
  - community
tags:
  - cloud native
  - containers
---

<a href="https://pixabay.com/en/louvre-pyramid-mesh-perspective-2189967/"><img aria-describedby="caption-attachment-2050" class="wp-image-2050 size-medium" src="https://blog.gingergeek.com/wp-content/uploads/2018/05/louvre-2189967_crop-98f00246a2776bae3338fdcb88b2badf-300x200.jpg" alt="" width="300" height="200" srcset="http://blog.gingergeek.com/wp-content/uploads/2018/05/louvre-2189967_crop-98f00246a2776bae3338fdcb88b2badf-300x200.jpg 300w, http://blog.gingergeek.com/wp-content/uploads/2018/05/louvre-2189967_crop-98f00246a2776bae3338fdcb88b2badf.jpg 720w" sizes="(max-width: 300px) 100vw, 300px" /></a><p id="caption-attachment-2050" class="wp-caption-text">Louvre mesh perspective (source: jraffin via Pixabay)</p></div>
<p><em><a href="https://www.oreilly.com/ideas/how-to-customize-an-istio-service-mesh" target="_blank" rel="nofollow noopener">Originally published</a> on April 26th, 2018 on O’Reilly.</em></p>
<p>Even though service meshes provide value outside of the use of microservices and containers, it&#8217;s in these environments that many teams first consider using a service mesh. The sheer volume of services that must be managed on an individual, distributed basis with microservices (versus centrally for a monolith) creates challenges for ensuring reliability, observability, and security of these services.</p>
<p>Adoption of a container orchestrator addresses a layer of infrastructure needs, but leaves some application or service-level needs unmet. Rather than attempting to overcome distributed systems concerns by writing infrastructure logic into application code, some teams choose to manage these challenges with a service mesh. A service mesh can help by ensuring the responsibility of service management is centralized, avoiding redundant instrumentation, and making observability ubiquitous and uniform across services.<span id="more-2049"></span></p>
<h2>Choosing a service mesh</h2>
<p>Factors such as your teams’ operational and technology expertise, existing observability, and access control tooling will influence the service mesh components, adapters, and deployment model you choose. Among others, Istio is a popularly adopted, open source service mesh. Some choose Istio (or any service mesh) for the automatic and immediate visibility it provides into top-line service metrics. In fact, many become hooked on service meshes for the observability they provide alone.</p>
<p>As a microservices platform, Istio is extensible through the way in which it offers choice of adapters and sidecars. Istio envelops and integrates with other open source projects to deliver a full-service mesh, which both bolsters its set of capabilities and offers a choice of which specific projects are included and deployed. Whether through Mixer adapters for observability or through swapping sidecars, Istio allows you to choose which components to include in your deployment.</p>
<h2>Customizing an Istio service mesh</h2>
<p>There are multiple deployment models you can use to lay down a service mesh. One of the most popular options is to deploy your service proxies as sidecars. Sidecarring your service proxy offers benefits like fine-grained policy enforcement and intra-cluster service-to-service encryption. This deployment model is the model of choice for Istio. Other Istio deployment choices include:</p>
<ul>
<li>Mixer adapters: typically used for integrating with access control, telemetry, quota enforcement, and billing systems.</li>
<li>Service proxies: abstract the network, translating requests between a client and service.</li>
</ul>
<p>Though Envoy is the default service proxy sidecar, you may choose another service proxy for your sidecar. While there are multiple service proxies in the ecosystem, outside of Envoy, only two have currently demonstrated integration with Istio: Linkerd and NGINX. The arrival of choice in service proxies for Istio has generated a lot of excitement. <a href="https://linkerd.io/getting-started/istio/" target="_blank" rel="nofollow noopener">Linkerd’s integration</a> was created early in Istio’s 0.1.6 release. Similarly, the <a href="https://github.com/nginmesh/nginmesh" target="_blank" rel="nofollow noopener">nginMesh</a> project has drawn much interest in the use of NGINX as Istio’s service proxy, as many organizations have broad and deep operational expertise built around this battle-tested proxy.</p>
<p><em>Learn more about how to deploy your sidecar (Istio proxy) of choice in the free webcast &#8220;</em><a href="https://www.oreilly.com/pub/e/3926?intcmp=il-data-webcast-lp-webcast_new_site_how-to-customize-an-istio-service-mesh_end_body_link_cta" target="_blank" rel="nofollow noopener"><em>Istio &#8211; The extensible service mesh</em></a><em>&#8220;.</em></p>
