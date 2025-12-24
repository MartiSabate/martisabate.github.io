---
layout: post
section-type: post
title: What are containers and why should you care about them
category: DEVSECOPS
tags: [ "DEVSECOPS" ]
---

# Introduction

Containers have become a foundational technology in modern software delivery, largely due to their portability, efficiency, and consistency across environments. 

Unlike traditional virtual machines, containers package applications together with their dependencies while sharing the underlying operating system, enabling faster startups, better resource utilization, and more reliable deployments. 

This article introduces the core concepts behind containers, explains how they differ from virtual machines, and explores common use cases and tools that shape today’s container ecosystem.

![](/img/What are containers and why should you care about them/Pasted image 20251224231032.png)

# What is a container?

First, let's see what is a container, and what value does it have in front of a traditional Virtual Machine:

Containers stand out primarily because of their portability. They are a form of operating system–level virtualization that allows applications and their dependencies to run in isolated processes. 

By packaging application code, configuration files, and required dependencies together, containers create lightweight, self-contained units that promote consistency across environments, improve operational efficiency, enhance developer productivity, and simplify version control.

Compared to virtual machines, containers are significantly smaller because they do not include a full operating system. Instead, they share the host’s virtualized OS while remaining isolated at the process level. 

This design enables faster startup times, reliable and repeatable deployments, and ensures that each container includes everything the application needs to run, such as libraries, system tools, code, and the runtime without unnecessary overhead.

![](/img/What are containers and why should you care about them/Pasted image 20251224231234.png)

## Key Characteristics of a container

- A single virtual machine can host multiple containers.
    - These containers run as daemonized processes within the host operating system.
- Containers allow you to maximize the use of available system resources, making infrastructure more cost-effective.
- Because containers share the same underlying operating system, they are more lightweight and efficient than running multiple virtual machines.
- Multiple applications can run side by side without being constrained by identical OS environments and without causing conflicts when sharing resources.

![](/img/What are containers and why should you care about them/Pasted image 20251224231308.png)

## Usual containers use cases

As seen above, containers are more lightweight than traditional virtual machines, leading to a resource optimization, here you will see some use cases that align well with these characteristics:

![](/img/What are containers and why should you care about them/Pasted image 20251224231331.png)

### Building microservices architecture

Containers are well suited for microservices architectures because they allow each service to be packaged, deployed, and scaled independently. 

By isolating services in separate containers, teams can use different languages, frameworks, and libraries without conflicts, while maintaining consistent runtime environments.

This approach improves fault isolation, simplifies scaling, and enables faster iteration and independent updates across services.

![](/img/What are containers and why should you care about them/Pasted image 20251224231523.png)

### Video rendering services

In video rendering workloads, containers provide a reliable way to run compute-intensive tasks in isolated environments. 

Rendering jobs can be distributed across multiple containers, making it easier to scale processing capacity on demand. 

Containers also ensure consistent configurations for codecs, libraries, and rendering tools, which helps produce predictable results and reduces setup time across different machines.

![](/img/What are containers and why should you care about them/Pasted image 20251224231543.png)

### Quick development and deployment

Containers significantly speed up development and deployment by ensuring that applications run the same way in development, testing, and production environments. 

Developers can quickly spin up containers with all required dependencies, reducing “it works on my machine” issues. 

This consistency enables faster testing, smoother CI/CD pipelines, and more frequent, reliable releases.

![](/img/What are containers and why should you care about them/Pasted image 20251224231556.png)

# Container technologies

Yes, this can be tought to process, so we have the fun thing here, the technologies we can use to achieve an easy click and run container flow.

![](/img/What are containers and why should you care about them/Pasted image 20251224231627.png)

## Docker

Docker is a containerization platform that enables developers to build, package, and run applications as containers in a consistent and repeatable way across different environments. 

It provides tools to create container images, manage dependencies, and run containers on any system that supports Docker, eliminating many environment-related issues. 

By abstracting infrastructure details and simplifying container workflows, Docker improves developer productivity, accelerates application delivery, and has become one of the most widely adopted technologies in the container ecosystem.

I do recommend using docker if you are starting with containers, it is very easy to use and very well documented!

![](/img/What are containers and why should you care about them/Pasted image 20251225000149.png)

## Kubernetes

Kubernetes is a container orchestration system. It is designed to manage, scale, and operate containerized applications in production environments.

While containers focus on packaging and running applications, Kubernetes operates at a higher level by automating deployment, scaling, load balancing, self-healing, and configuration management.

It is a core component of modern cloud-native and DevSecOps architectures, enabling teams to run large numbers of containers reliably while enforcing security policies, resource control, and high availability across distributed systems.

![](/img/What are containers and why should you care about them/Pasted image 20251225000049.png)

## Other Technologies

I have just explained what is Docker and Kubernetes here, but keep in mind there are lots of technologies out there, for this reason I made a list of some of them:

- **containerd** – Core container runtime used by Kubernetes
- **CRI-O** – Kubernetes-native container runtime
- **Lima** – Container and VM environment for macOS (often used with containerd)
- **gVisor** – User-space kernel for container sandboxing
- **Kata Containers** – Lightweight VM-based container isolation
- **Firecracker** – MicroVM technology used for container and serverless isolation
- **Incus** – System container and VM manager (successor to LXD)
- **BuildKit** – Container image build engine (Docker / OCI builds)
- **Podman Container Tools** – Podman ecosystem tools (build, compose, system, etc.)
- **rkt (rocket)** – Application container runtime (deprecated but historically relevant)
- **Sysbox** – Secure container runtime enabling “containers-as-VMs”
- **bootc** – Image-based OS and container boot management for immutable systems
- **Hyperlight** – Lightweight VM-based isolation for running untrusted workloads
- **Inclavare Containers** – Confidential containers using hardware-backed enclaves (TEE)
- **Kuasar** – Next-generation container runtime with pluggable sandboxing backends
- **urunc** – OCI-compatible runtime for confidential and enclave-based containers
- **Virtual Kubelet** – Kubernetes kubelet implementation for virtual/containerless nodes
- **Interlink** – Kubernetes abstraction layer for off-cluster and virtualized workloads
- **WasmEdge Runtime** – WebAssembly runtime optimized for cloud-native and Kubernetes
- **youki** – OCI-compliant container runtime written in Rust

![](/img/What are containers and why should you care about them/Pasted image 20251225000208.png)

# Final thoughts

In summary, containers provide a modern, efficient approach to building, running, and deploying applications by combining portability, consistency, and optimal resource usage. 

Whether powering microservices architectures, scaling compute-intensive workloads like video rendering, or accelerating development and deployment workflows, containers help teams deliver software faster and more reliably.

As container ecosystems and tools continue to evolve, understanding these fundamentals is a key step toward designing scalable, cost-effective, and resilient systems.

As always, feel free to contact me through any social media if you would like to get further details, I will be more than happy to help you!

![](/img/What are containers and why should you care about them/Pasted image 20251224231850.png)
