---
layout: post
section-type: post
title: Metasploit Framework
category: Cybersecurity
tags: [ "Cybersecurity"]
---


# Metasploit Framework

The Metasploit Framework is a powerful open-source platform used by security professionals to identify, test, and validate system vulnerabilities. It provides a comprehensive suite of tools for developing and executing exploit code against remote targets in a controlled and ethical manner. In this blog, we will explore what Metasploit is, how it works, and why it plays a critical role in modern cybersecurity testing.

![](/img/Metasploit Framework/Pasted image 20260215224522.png)
# What is the Metasploit Framework?

The Metasploit Framework (MSF) is a robust, open-source penetration testing and exploitation framework widely used by security professionals and researchers worldwide. It provides a comprehensive infrastructure that enables automation across every stage of the penetration testing lifecycle, from reconnaissance to post-exploitation. Additionally, it serves as a platform for developing and testing exploits and maintains one of the world’s largest collections of publicly available, tested exploit modules.

![](/img/Metasploit Framework/Pasted image 20260215224628.png)

## The Metasploit Framework Architecture

The Metasploit Framework is designed with a modular architecture, enabling new features and functionalities to be added easily and efficiently, making it highly adaptable to evolving security testing needs.

![](/img/Metasploit Framework/Pasted image 20260215223345.png)

### Metasploit Framework File System Structure

On Linux systems, the Metasploit Framework stores its default modules in the `/usr/share/metasploit-framework/modules` directory. 

Custom or user-defined modules, on the other hand, are typically placed in the `~/.ms4/modules` directory, allowing users to extend the framework’s functionality without modifying the core installation files.

![](/img/Metasploit Framework/Pasted image 20260215224752.png)
### The Metasploit Framework Modules

#### Auxiliary

Within the Metasploit Framework, supporting components such as scanners, crawlers, and fuzzers are implemented as auxiliary modules. These modules provide functionality for tasks including scanning, service discovery, and fuzz testing, without requiring an exploit payload. Auxiliary modules can be used during both the information gathering phase and the post-exploitation phase of a penetration test, including discovering additional hosts and performing port scans across network subnets after initial access has been obtained.

![](/img/Metasploit Framework/Pasted image 20260215225033.png)

#### Encoders

Encoders are used to transform exploits and payloads in an attempt to evade signature-based detection mechanisms. Signature-based antivirus solutions rely on databases of known threat signatures and generate alerts when a match is identified. However, the effectiveness of encoders can be limited, as modern security solutions often incorporate additional detection techniques, such as heuristic and behavioral analysis, beyond simple signature matching.

![](/img/Metasploit Framework/Pasted image 20260215225144.png)
#### Evasion

Encoders are primarily designed to modify the structure of a payload to ensure proper execution and compatibility, rather than serving as a guaranteed method of bypassing antivirus defenses. In contrast, evasion modules are specifically developed to attempt to circumvent security detection mechanisms, though their success varies depending on the target environment and the sophistication of the defensive controls in place.

![](/img/Metasploit Framework/Pasted image 20260215225426.png)
#### Exploits

Exploits are systematically organized based on their target platform and service, making it easier for penetration testers to identify and deploy the appropriate exploit for a specific operating system, application, or network service.

![](/img/Metasploit Framework/Pasted image 20260215225639.png)

#### NOPs

NOPs (No Operation instructions) are assembly instructions that perform no action when executed. In the Intel x86 architecture, a NOP is commonly represented by the hexadecimal value `0x90`, causing the CPU to do nothing for a single cycle. NOP instructions are often used as padding, such as in NOP sleds, to help maintain consistent payload sizes and improve reliability during exploit execution.

![](/img/Metasploit Framework/Pasted image 20260215225817.png)

#### Post

Post modules are primarily used during the post-exploitation phase of a penetration test. After initial access has been established, these modules assist with tasks such as privilege escalation, information gathering, persistence mechanisms, and lateral movement within the target environment.

![](/img/Metasploit Framework/Pasted image 20260215230003.png)
# Metasploit Framework Payloads

In the Metasploit Framework, payloads are pieces of code executed on a target system after a vulnerability has been successfully exploited. While exploits leverage specific weaknesses to gain access, the payload determines the actual outcome, such as executing a command, opening a shell, deploying a backdoor for controlled testing, or launching an application like `calc.exe` as a benign proof of concept in a penetration test report.

Executing a single command demonstrates code execution capability; however, establishing an interactive session provides significantly greater control. This interactive command-line connection, known as a _shell_, allows testers to send and execute multiple commands dynamically. Metasploit supports various payloads specifically designed to establish such shells on compromised target systems, enabling more comprehensive post-exploitation activities.

![](/img/Metasploit Framework/Pasted image 20260215231935.png)

## Payload Directories within Metasploit Framework

You will see three different directories under payloads: singles, stagers and stages

![](/img/Metasploit Framework/Pasted image 20260215231950.png)
### Adapters

Adapters are used to wrap single payloads and transform them into alternative formats suitable for specific delivery methods. For example, a standard single payload can be encapsulated within a PowerShell adapter, generating a single PowerShell command that executes the embedded payload when run on the target system.

![](/img/Metasploit Framework/Pasted image 20260215232058.png)
### Singles

Single payloads are self-contained payloads that execute independently without requiring the download of additional components. Examples include adding a user account or launching an application such as `notepad.exe`, where all necessary functionality is embedded directly within the payload itself.

![](/img/Metasploit Framework/Pasted image 20260215232116.png)

### Stagers

Stagers are responsible for establishing the initial communication channel between the attacker’s system and the target. They are used as part of staged payloads, where a small stager component is first delivered to the target system.

Once executed, the stager downloads the remaining portion of the payload, known as the _stage_. This approach offers advantages such as a smaller initial payload size, which can improve delivery reliability and, in some cases, reduce detection compared to sending the full payload in a single transmission.

The Stage is downloaded by the Stager. It will allow you to use larger sized payloads.

![](/img/Metasploit Framework/Pasted image 20260215233345.png)

## Types of Payloads within Metasploit Framework

There are two primary types of payloads can be paired with an exploit: **single (inline) payloads** and **staged payloads**. Single payloads are self-contained and execute entirely on their own, while staged payloads deliver a small stager first, which then retrieves the remaining payload components from the attacker’s system:

![](/img/Metasploit Framework/Pasted image 20260215232006.png)

### Non-Staged Payloads

A **non-staged payload** (also known as a single payload) is delivered to the target system in its entirety together with the exploit. It is self-contained and does not require downloading additional components after execution, as all necessary functionality is embedded within the payload itself.

![](/img/Metasploit Framework/Pasted image 20260215233617.png)
### Staged Payloads

A **staged payload** is delivered to the target system in two distinct components. The first part, known as the **stager**, establishes a reverse connection back to the attacker’s system. Once this communication channel is in place, the stager downloads the second component, the **stage**, which contains the full payload functionality and executes it on the target system.

![](/img/Metasploit Framework/Pasted image 20260215233753.png)

## Essential Terminology

- **Interface** → Methods of interacting with the Metasploit Framework
- **Module** → A piece of code that performs a specific task; for example, an exploit is a type of module
- **Vulnerability** → A weakness or flaw in a computer system, network, service, or application that can be exploited
- **Exploit** → A piece of code or module designed to take advantage of a vulnerability within a system, service, or application
- **Payload** → Code delivered to the target system by an exploit, intended to execute commands or establish remote access
- **Listener** → A utility that waits for and accepts an incoming connection from a target system

![](/img/Metasploit Framework/Pasted image 20260215232017.png)

## Metasploit Framework Interfaces
![](/img/Metasploit Framework/Pasted image 20260215232039.png)
### Metasploit Framework Console

The Metasploit Framework Console (MSFconsole) is an all-in-one, user-friendly interface that provides full access to the features and functionality of the Metasploit Framework. It enables users to load and configure modules, manage payloads, establish listeners, and control exploitation and post-exploitation activities from a centralized command-line environment.

### Metasploit Framework CLI
> Please note that Metasploit Framework CLI is discontinued since 2015

The Metasploit Framework Command Line Interface (MSFcli) is a command-line utility designed to facilitate the creation of automation scripts that leverage Metasploit modules. It allows users to execute modules directly from the terminal and can be integrated with other tools by redirecting input and output between MSFcli and external utilities, enabling more flexible and automated workflows.

### Metasploit Community Edition

The Metasploit Community Edition is a web-based graphical user interface (GUI) front-end for the Metasploit Framework. It is designed to simplify tasks such as network discovery and vulnerability identification by providing a more accessible and streamlined interface compared to the command-line console.
# Metasploit Framework for Penetration Testing 

## First Steps

### Run Metasploit

- `sudo msfdb run`
	- Start Metasploit Database
	- Start Metasploit Framework

### Create a Database

In order to achieve this, you will need to have PostgreSQL already installed in your system

1. `msfdb init --connection-string=postgresql://postgres@localhost:5432/postgres`
2. Inside metasploit > `db_connect postgres:<password>@localhost:5432/postgres`
	1. Use the system `postgresql` user credentials for this command

### Make a port scan with Metasploit Framework

1. Launch a nmap scan through metasploit
	1. Example: `nmap 192.110.123.0/24`

### Exploit a vulnerable service

After seeing a vulnerable service through the previous scan, load an exploit and configure it

1. Run Metasploit (db already loaded): `msfconsole`
2. Select the exploit: `use exploit/unix/webapp/xoda_file_upload`
3. Configure the exploit
	1. Configure the target exploit IP address: `set RHOSTS 192.120.121.3`
	2. Some exploits may require further configuration, this depends on their nature: `set TARGETURI /`
4. Execute the exploit after its configuration: `run`

### Get a Reverse Shell

Usually, after an exploitation within Metasploit Framework, you would expect getting a meterpreter shell, which will allow you to control remotely the target machine
# Armitage

The Armitage is a free, Java-based graphical user interface (GUI) front-end for the Metasploit Framework that simplifies network discovery, exploitation, and post-exploitation activities. It provides visual target mapping, automates port scanning, streamlines exploitation workflows, and supports automated post-exploitation tasks through an intuitive interface.

To function correctly, Armitage requires the Metasploit database and backend services to be enabled and running. It comes pre-packaged with Kali Linux and is also included in various other penetration testing distributions.

![](/img/Metasploit Framework/Pasted image 20260215230353.png)

# End of the article

I hope this article was useful and entertaining for you ^^



