---
layout: post
section-type: post
title: Firewalls, more than just a wall
category: DevSecOps
tags: [ "DevSecOps" ]
---

# Firewalls, more than just a wall

Hello again ^^

I am happy to see your interest in this field. I am going to explain and categorize firewalls here, no technical explanation, but fundamental, trust me. Lets start:

![](/img/Firewalls, more than just a wall/Pasted image 20260104210449.png)
# What is a Firewall?

Let's start with the basic definition, if you are here I understand you don't need a basic definition of what is a firewall, so lets just have here the definition for reference:

A firewall is a piece of network equipment. It is a critical security component positioned between the internet "considered an untrusted network" and the internal network. 

> The primary function of a firewall is to permit or deny network traffic based on predefined rules.

Although firewalls exist in various forms, the most widely used and recognized type is the hardware-based network firewall. However, merely deploying a firewall device is not sufficient to protect a network from external threats, as attackers can still penetrate networks that use firewalls. Proper configuration is essential. Incorrect or incomplete firewall settings can not only degrade network performance but also introduce serious security vulnerabilities.

Firewalls can enforce security by defining rules that permit or deny traffic through the use of access control lists, an understanding of ports and protocols, or by implementing screened subnets.

![](/img/Firewalls, more than just a wall/Pasted image 20260104211111.png)
# Firewall deployement models

I will expose here the difference between a physical firewall and a virtual firewall:

![](/img/Firewalls, more than just a wall/Pasted image 20260104211325.png)

## Physical Firewall

A physical firewall is a hardware-based security solution that runs on a dedicated appliance instead of software installed on a general-purpose computer, enabling it to operate independently from the systems it protects. It is commonly deployed at the network boundary, such as gateways, data centers, or the edge of an enterprise network, where it acts as a centralized point for managing inbound and outbound traffic. The device conducts traffic inspection by evaluating network packets against predefined rules involving IP addresses, ports, protocols, and, in more advanced models, application- or content-level information. Because it is purpose-built, a physical firewall provides greater separation from host systems and typically delivers superior performance and throughput compared to software-based firewalls, making it suitable for environments that demand high levels of security and reliability.

![](/img/Firewalls, more than just a wall/Pasted image 20260104211417.png)

## Virtual Firewall

A virtual firewall performs packet filtering within a virtualized environment, regulating and controlling both inbound and outbound network traffic. It functions in a manner similar to a physical firewall. When used to secure cloud infrastructure and services, a virtual firewall is usually configured on a per–server instance basis. This approach differs significantly from firewall as a service (FWaaS), which is intended to secure the network perimeter as well as remote users. Virtual firewalls are specifically designed to protect cloud-based servers from malicious traffic or external attacks.

![](/img/Firewalls, more than just a wall/Pasted image 20260104211620.png)

# Firewall types

Here I am going to show you different types of firewalls. Please understand this section as different firewalls that have different end purposes each, for this reason  you will have to understand precisely the context to choose the right one that fit your needs:

![](/img/Firewalls, more than just a wall/Pasted image 20260104212754.png)
## Host-based Firewall

You can refer this are the internal firewall of your host machine, such as the Windows Firewall. It secures individual endpoints, such as a personal computer.

It is best suited for protecting personal devices, as it runs directly on the desktop system.

![](/img/Firewalls, more than just a wall/Pasted image 20260104212929.png)
## Network-based Firewall

It protects complete networks along with their access points.

It is well suited for securing network boundaries by preventing unauthorized access.

![](/img/Firewalls, more than just a wall/Pasted image 20260104213125.png)

## Stateless Firewall (OSI Layer 4)

A stateless firewall operates using a fixed set of rules that permit or deny network traffic based solely on basic packet attributes such as source and destination IP addresses, port numbers, and protocols. 

It examines only this header-level information and does not maintain any awareness of connection states, meaning it cannot distinguish between new, established, or related connections. As a result, it does not validate inbound or outbound connection status, verify completion of the TCP three-way handshake, or perform deep packet inspection of payload contents. 

While this simplified design makes a stateless firewall highly efficient and fast, it also limits its ability to detect complex or context-based attacks, offering a lower level of security compared to a stateful firewall.

A stateless firewall is most appropriate for basic traffic filtering scenarios where speed and performance are prioritized over detailed traffic analysis. It is commonly deployed in high-throughput environments that require rapid packet processing with minimal latency, or used as a preliminary filtering layer in front of a more advanced firewall to reduce unnecessary traffic and improve overall network efficiency.

![](/img/Firewalls, more than just a wall/Pasted image 20260104213254.png)
## Stateful Inspection Firewall

A stateful firewall monitors the state of active network connections, allowing it to determine whether an incoming packet is part of an existing and legitimate session. By maintaining contextual information in connection state tables, it makes more informed filtering decisions based on traffic flows rather than evaluating packets in isolation. 

This approach provides stronger security, as it can better detect and block spoofed packets and mitigate certain types of denial-of-service (DDoS) attacks that rely on illegitimate or abnormal connection behavior.

A stateful firewall is well suited for scenarios where legitimate traffic must be permitted based on connection state, such as allowing only response traffic to previously initiated outbound connections.

It is widely used in enterprise environments because it provides an effective balance between performance efficiency and enhanced security, offering greater protection than basic filtering while maintaining acceptable processing overhead.

![](/img/Firewalls, more than just a wall/Pasted image 20260104213517.png)

## Web Application Firewall (WAF) (OSI Layer 7)

A web application firewall (WAF) protects web applications hosted on web servers by detecting and blocking malicious activity that targets application-level vulnerabilities. It analyzes HTTP and HTTPS traffic in detail and enforce security policies specific to web applications.

A web application firewall (WAF) is crucial for defending web applications against common online threats such as SQL injection, Cross-Site Scripting (XSS), and distributed denial-of-service (DDoS) attacks. By inspecting application-layer traffic in depth, it can identify malicious patterns and behaviors that traditional network firewalls are unable to detect, thereby significantly enhancing the security of web-facing services.

![](/img/Firewalls, more than just a wall/Pasted image 20260104213716.png)

## Unified Threat Management Firewall (UTM)

A unified threat management (UTM) solution is a multifunctional security platform that combines malware inspection, content filtering, and URL filtering into a single system. 

It is capable of delivering a wide range of security services, including malware detection, data loss prevention (DLP), content control, and URL filtering, all from one centralized platform. 

UTM solutions are commonly chosen when an integrated, all-in-one approach is desired, as they simplify deployment, management, and oversight of organizational security controls.

It is best suited for situations where a comprehensive, all-in-one security solution is required. By consolidating multiple security functions into a single platform, it simplifies security management while providing broad protection, making it especially effective for environments that need centralized control without deploying multiple specialized systems.

![](/img/Firewalls, more than just a wall/Pasted image 20260104214001.png)

## Next-Generation Firewall (NGFW)

A next-generation firewall (NGFW) is a highly advanced network security solution that  leverages cloud-based threat intelligence. 

It is application-aware, allowing it to identify, analyze, and control network traffic at the application level, while using cloud-powered intelligence to enhance threat detection and protection against sophisticated and emerging cyber threats.

It is ideal for environments with advanced security requirements, as it provides intrusion prevention and comprehensive protection across both on-premises and cloud infrastructures. By combining deep application awareness with intelligent threat detection, it enables organizations to defend against complex attacks while maintaining visibility and control over modern, distributed network environments.

![](/img/Firewalls, more than just a wall/Pasted image 20260104214228.png)

## Application Firewall (OSI Layer 7)

It examines network traffic at the application layer, enabling deep packet inspection to detect and manage specific applications, user activities, and content. This capability strengthens security and control in modern network environments by providing granular visibility into traffic patterns and allowing precise enforcement of security policies against sophisticated threats.

It can prevent access to sensitive paths such as **/admin** URLs and filter malicious SQL injection attempts embedded within HTTP requests. By inspecting application-layer traffic in real time, it enforces security rules that block unauthorized access and detect malicious input patterns, helping protect web applications from exploitation and unauthorized control.

![](/img/Firewalls, more than just a wall/Pasted image 20260104220812.png)

# Final words

To conclude, firewalls are not a one-size-fits-all security solution but a broad family of technologies, each designed to address specific security needs, environments, and threat models. 

Understanding the fundamental differences between deployment models and firewall types is essential to making informed decisions rather than relying on assumptions or marketing terms (very common sadly). 

The effectiveness of a firewall depends not only on its category or sophistication but also on how well it is chosen for its context and how carefully it is configured and maintained. When used correctly and as part of a layered security strategy, firewalls remain a foundational pillar of modern network defense, providing visibility, control, and protection in an increasingly complex threat landscape.

![](/img/Firewalls, more than just a wall/Pasted image 20260104221013.png)

