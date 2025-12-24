---
layout: post
section-type: post
title: Cloud Computing From Zero to Secure recommendations
category: Cloud
tags: [ "cloud" ]
---

# Introduction

Hello everyone!

I hope you are doing well. In today's post I am going to share you what is the Cloud, starting from the basics, and continuing to general security recommendations.

Cloud Security Management is a very wide field, detailing every aspect of it in this post would be too large for anyone to read, for this reason I did my best to simplify all the explanations to be simple and direct to the key point for each one of them.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221192259.png)

## Should you read this?

In order to address correctly this information, avoiding you losing your time reading information you might not need, I have addressed this post for anyone who:
- Would like to work in Cloud Computing
- Would like to identify security issues within his corporate cloud systems and resolve them
- Is interested in a high level vision for any cloud 
- Is using on-prem systems and is thinking into moving to the Cloud in an uncertain future

Said this, let's just start, shall we? ;)

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221192411.png)

# The basics

I am sure that if you are here, you have already been in IT for some time, however, I believe the best approach on a high level vision starts with the basics, I will be as brief as I can:

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221192552.png)

## What is Cloud Computing?

Cloud computing is nothing else that servers hosted in a data center somewhere in the world. It is the best approach nowadays to start any online service easily from a few clicks, scalable and flexible by design. A part from these benefits, Cloud Computing shines for it's cost-effective model, in which you only pay for the resources that you need, this differentiates completely Cloud and on-prem hosting.

No hardware management is needed, this may very depending on Cloud Service Provider (CSP) you are using. I will mention the most famous CSPs later in this post.

Additionally, you can manage the Cloud from anywhere: from your home, from the office, or even in the public transport, you only need a device connected to internet in order to deploy infrastructure manage your online applications.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221192658.png)

## Cloud Computing deployment models

Now we have a basic idea of what is Cloud Computing why is it better following this path (in most of the cases) rather than on-prem, let's see the main different types of Cloud deployment models:

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221192805.png)

### Public Cloud

This is the most common model, where in the CSP hosts multiple tenants, sometimes on the same hardware.

As per it's definition, you should consider an unavoidable risk which consist in the fact that as multiple organizations are hosted on the same machine, the actions of one tenant can impact the actions of another, and your organization could be impacted by someone else actions without any predictable signal of it.

It is known as Multi-tenant Cloud, Cloud-Native, or Cloud First.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195408.png)

### Private Cloud

Through this model, CSPs host specific hardware for your corporation, separated from other machines used by other companies. This model is more secure than the multi-tenant one, as you can understand.

Private Cloud is also called on-prem, but keep in mind that all on-prem private clouds are on-premise, but not all on-premise environments are private clouds. To clarify, on-prem private clouds have cloud functionalities as its operating model.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195655.png)

### Cross Cloud / Community Cloud

This is a very cost-effective model:

A community cloud is a private cloud shared by multiple organizations that have common requirements, such as:
- Regulatory obligations
- Security standards
- Industry-specific compliance
- Mission objectives

It is not public, but it is also not single-tenant in the organizational sense.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195630.png)

### Hybrid Cloud

The Hybrid Cloud consists of a mix of using both on-premise and cloud infrastructures. A use case for this model is based on systems that generate data on-premise, and may expose the company services through cloud applications.

This model is ideal for companies that decide not to host all of their organization in the cloud. 

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193054.png)

## Types of Cloud Computing

Now we have seen what cloud deployment options are available out there, but for any of these models, all the services it offer functions that are meant to replicate functions that in the past were provided on-prem. 

The idea behind cloud services is to optimize costs for the specific function (i.e. storage services) and the infrastructure management.

Those are segmented as:

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193307.png)

### Infrastructure as a Service (IaaS)

The CSP will supply the network infrastructure, including desktops, servers, storage systems, firewalls, routers, and switches—that is, the physical hardware components of the network. These devices are delivered with default factory configurations, which must be modified to align with the organization’s operational and security requirements. The customer is responsible for installing the operating systems and for configuring, securing, and applying patches to the devices.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193520.png)

### Software as a Service (SaaS)

Software as a Service (SaaS) is a cloud delivery model in which the CSP hosts a predefined, centrally managed software application that users access via a web interface. Examples include GoldMine, Salesforce, and Microsoft 365. The underlying application code and core functionality cannot be modified by the customer.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193527.png)

### Platform as a Service (PaaS)

Platform as a Service (PaaS) provides developers with a complete cloud-based environment for building, testing, and deploying applications without the need to manage underlying infrastructure.

These platforms deliver an integrated set of tools and services that support application development and deployment across multiple operating systems and devices, including iOS, Android, and Windows.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193532.png)

### Security as a Service (SECaaS)

Security as a Service (SECaaS) delivers Identity and Access Management (IAM) capabilities that enable secure, authorized access to applications from any location at any time. In addition, a managed security service provider supplies dedicated security personnel to operate and oversee these services.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193537.png)

### Integration Platform as a Service (IPaaS)

Integration Platform as a Service (iPaaS) is a cloud-based service model designed to connect, integrate, and automate data flows between disparate applications, systems, and data sources.

An example of IPaaS service is Zapier.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193542.png)

### Infrastructure as a Code (IaC)

Infrastructure as Code (IaC) is the practice of provisioning and managing IT infrastructure using machine-readable definitions (through code) rather than manual processes. These definitions are typically written in declarative formats such as YAML or JSON.

Through IaC you can deploy infrastructure through code, being this process easire to scalate, being more reliable on its deployment and more operationally efficient.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193551.png)

### Anything as a Service (XaaS)

Anything as a Service (XaaS) encompasses a broad range of cloud-based service offerings, including Network as a Service (NaaS), Desktop as a Service (DaaS), Backup as a Service (BaaS), and numerous other service models.

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193557.png)

## Cloud Service Providers

As explained above, Cloud services are offered from the Cloud Service Providers, that are those companies who take some of the responsibilities of the infrastructure maintenance allowing companies to focus only in their needs to develop and deploy applications.

The services provided by CSPs can be chained together to create cloud architectures.

Here I will expose some of the most recognized CSPs available nowadays in the market segmented in some categories

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221193836.png)

#### Most recognized CSPs in the industry

These are the most known CSPs nowadays. These offer services that most of the companies can take profit to enhance their business processes and applications:

- Amazon Web Services
- Google Cloud Platform
- Microsoft Azure
- Alibaba Cloud

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195257.png)

#### Tech Specialized CSPs

This list include some CSPs that offer more in depth tech specialized services, such as high-performance databases, enterprise legacy and regulated environments, and much more:

- IBM Cloud
- Oracle Cloud
- Rackspace (OpenStack)

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195454.png)

#### Simple, cost-effective CSPs

Also known as Virtual Private Servers (VPS) turned into an IaaS offer, these CSPs offer simple and cost effective solutions usable by anyone:

- Vultr
- Digital Ocean
- Linode

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195603.png)

# The end

I hope you enjoyed and learned something new through this Cloud Computing overview.

I would like to encourage anyone to contact me asking for specific recommendations if you would like custom assistance on this matter, I will be more than happy to assist!

![](/img/Cloud Computing From Zero to Secure recommendations/Pasted image 20251221195800.png)
