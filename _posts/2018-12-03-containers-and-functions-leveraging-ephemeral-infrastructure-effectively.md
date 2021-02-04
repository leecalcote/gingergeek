---
id: 1798
title: Containers and Functions - Leveraging Ephemeral Infrastructure Effectively
date: 2018-12-03T012:06:15+00:00
author: Lee
excerpt: With containers, microservices and functions interweaving through modern application design, diligence is necessary to make sure you’re successfully navigating when to use containers and functions as application packaging technologies and how to employ post-deployment techniques. Wrangling with Container Management? Read on.
layout: post
guid: http://blog.gingergeek.com/?p=1798
permalink: /2018/04/containers-and-functions-leveraging-ephemeral-infrastructure-effectively/
categories:
  - cncf
  - community
tags:
  - cncf
  - community
---

<i>Originally published on Container Journal on December 3rd, 2018.</i>

With containers, microservices and functions interweaving through modern application design, diligence is necessary to make sure you’re successfully navigating when to use containers and functions as application packaging technologies and how to employ post-deployment techniques.

We all know this can be daunting—it’s an ephemeral world out there. Establishing a delivery pipeline and streamlining workflow for microservices is key to achieving benefits from containers and functions at both an operational level for confidence of resiliency, performance and so on, and at a strategic business level for competitive advantages of speed, flexibility and more.

Let’s explore several universal best practices for succeeding in the ephemeral world of containers and functions, and walk through a few of the ins and outs of discerning befitting use of serverless computing. Then, in my next blog post, we’ll look at how to harness the value promised by incorporation of a service mesh into your stack.

Incorporating Orchestration: Wrangling Container Management

Given their near-ubiquitous adoption, container formats and their runtime engines have effectively standardized and stabilized as reliable and interoperable infrastructure. Organizations of all sizes have been running containers in production for a number of years now. Their success in operating containerized workloads in complex ways may be largely attributed to the capabilities of container orchestrators.

As I described when contrasting and comparing container orchestrators, use of a container orchestrator addresses much of layer of infrastructure needs, it does not meet all application or service-level requirements. Isn’t that why we run infrastructure? To serve the application? With that rhetorical question asked, container orchestrators have necessarily focused first on infrastructure level concerns, critical to ensuring robust management of the underlying substrate of distributed systems challenges.

Use of a container orchestrator does not meet all application or service-level requirements. Isn’t that why we run infrastructure? To serve the application? With that rhetorical question asked, container orchestrators have necessarilyfocused first on infrastructure-level concerns, critical to ensuring robust management of the underlying substrate of distributed systems challenges.

Unfortunately, this leaves a number of distributed systems concerns for developers to address. Until recently, developers have largely addressed these concerns by writing infrastructure logic into application code—things such as circuit breaking, timeouts and retries—employing client-side libraries to do so. In my second part in this series, I’ll highlight how DevOps teams can manage the layer of challenges unaddressed by container orchestrators using a service mesh. For now, let’s turn our focus to another ephemeral piece of infrastructure—functions.

Costs and Benefits of Serverless Computing

Many of you have become comfortable running multiple containers and are now looking to transcend containers and microservices, augmenting your stack by interweaving functions. Writing individual functions to complete specific tasks is appealing, as doing so facilitates faster startup times, better resource utilization, finer-grained management, flexible and precise scaling and no provisioning, updating or managing server infrastructure. However, certain use cases are better-suited for serverless computing than others. Testing, startup latency, debuggability and cost all must be considered when deciding if serverless is the right fit for an environment.

The notion of running a function to perform a task and only paying for the execution time needed to run that task is veryappealing. As functions take foothold with your applications, exercise caution with respect to serverless pricing models, as cost accumulates quickly. Costs can accrue in short order when either a given function enjoys too much success (is invoked well beyond the number of times initially accounted for), particularly if the execution of one function in turn calls other many functions (or, perhaps, calls back to itself, creating an endless loop of execution). It’s therefore important to understand how many times the function is going to be invoked when deciding if serverless is the right fit. Functions are best-suited for a task that’s run under a short time period. Be conscientious when calling a function from another function: You run the risk of doubling your cost and increasing the complexity of debugging your software as it divides into more and smaller units of independent execution.

FaaScinating Use Cases

The architectural pattern of the use of functions follows an event-driven design, typically persisting output/results from a function to a datastore or queue that in turn triggers the next function (if needed). When ascribing to this pattern, treat all data as though it is in motion, not at rest, at any point during the execution of your function.

It’s best to consider serverless when a workload is: asynchronous; concurrent; easy to parallelize into independent units of work; infrequent or with sporadic demand; with large, unpredictable variance in scaling requirements; stateless; ephemeral; without a major need for instantaneous cold start time; or highly dynamic in terms of changing business requirements that drive a need for accelerated developer velocity. Example workloads that readily benefit from serverless architectures include:

Executing logic in response to database changes (insert, update, trigger, delete).
Performing analytics on IoT sensor input messages, for example, as Message Queuing Telemetry Transport (MQTT) messages.
Handling stream processing (analyzing or modifying data in motion).
Managing single time extract, transform, and load jobs that require a great deal of processing for a short time.
Providing cognitive computing via a chat bot interface (asynchronous, but correlated).
Scheduling tasks performed for a short time (e.g., cron or batch style invocations).
Serving machine learning and AI models (retrieving one or more data elements such as tables or images and matching against a pre-learned data model to identify text, faces, anomalies, etc.).
Continuous integration pipelines that provision resources for build jobs on-demand, instead of keeping a pool of build slave hosts waiting for jobs to be dispatched.
Universal Tips for Successfully Navigating an Ephemeral World

As application packing technologies, both containers and functions have their own caveats, so knowing how and when to leverage them is key. In your organization, you can apply four universally applicable best practices to packaging, running, deploying and operating containers and functions, including:

Prioritize Observability: When writing an application for containers, particularly in the case of a microservices design, it’s crucial to ensure both your orchestration and application layers are observable to ensure they expose key metrics about the performance of your infrastructure and application, so that you may reason over their health as needed.
Adopt Modern Tooling: Containers, microservices and functions pose different application development patterns than you may have traditionally encountered, so the right tooling is not always available. However, it’s crucial to adopt monitoring and debugging tools that can support these application development patterns, to help ensure success in deployment and running workloads.
Application Design: The modern application development landscape is ephemeral; a function will come and go, a container will come and go, and applications must be designed to support this life cycle. For functions specifically, you can run into issues with incorrect logic and end up having functions fall into a vicious cycle of calling each other, billing spikes and generally not working effectively.
Fit Your Use Case: How many of the characteristics listed above apply to your user case? Is this use case or your application well-positioned for these ephemeral execution environments?
Conclusion

At first, the idea of running a function to perform a task and only paying for the execution time needed to run that task is attractive. However, this pricing model can become expensive if you are executing many functions or running a specific function millions of times. With that in mind, it’s crucial to understand how many times the function is going to be invoked when deciding if serverless is the right fit—lengthy batch-processing tasks may not be the best fit for use of a function; functions are better-suited for a task that’s run under a short time period.

As containers, microservices and functions become even more integrated into hybrid and cloud environments, you must remain diligent to ensure you’re navigating these aspects of the modern application development landscape successfully. Implementing several universal best practices including prioritizing observability, adopting modern DevOps monitoring tools, application design and knowing specific use cases can all help you succeed in the world of containers, microservices and functions.