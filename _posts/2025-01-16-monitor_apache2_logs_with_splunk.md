---
layout: post
section-type: post
title: How to monitor Apache2 logs with an Universal Forwarder in Splunk
category: SOC
tags: [ "SIEM", "SPLUNK" ]
---

How to monitor Apache2 logs through Splunk, and generate a dashboard to detect possible attacks.

This is a lab where I install in an Ubuntu machine a Splunk SIEM, Splunk Universal Forwarder, and configure it in order to retrieve apache2 logs, and filter them through a dashboard through regex in order to filter SQLi attempts.



# Installation

To install Splunk and Splunk Forwarder an account is required to be created in https://splunk.com. I have downloaded Splunk Enterprise https://www.splunk.com/en_us/download/splunk-enterprise.html deb file, and installed it through dpkg:

`sudo dpkg -i splunk-9.5.0-6b4ebe426ca6-linux-amd64.deb`

Same procedure for the forwarder

`sudo dpkg -i splunkforwarder-9.5.0-6b4ebe426ca6-linux-amd64.deb`


![](/img/splunkSiemImages/IMG1)

Once both are installed, first, splunk should be started through the following command:

`sudo /opt/splunk/bin/splunk start`

This will require accepting the terms, and creating an administrator user with a password. Then the web server will be available on http://127.0.0.1:8000

![](../../../../splunkSiemImages/IMG2)


After this, the port 9997 would need to be open in order to receive data from the forwarder. This can be achieved in http://127.0.0.1:8000/en-US/manager/launcher/data/inputs/tcp/cooked

Or accessing in Settings>Forwarding and receiving>Receive Data

And adding the port by pressing "New Receiving Port"

![](../../../../splunkSiemImages/IMG3)


This configuration will allow splunk to receive data from forwarders.

To continue, it is required to create in the forwarder an inputs.conf file with the configuration of the data. To achieve this, I have taken reference of the following manual https://github.com/awais922609/Defensive-Learning/blob/main/Linux_Commands_for_Splunk_Configurations.pdf; however, further details regarding this file are well explained in the official documentation https://docs.splunk.com/Documentation/Splunk/9.4.0/Admin/Inputsconf


In my case, the host name is ubuntu2404. It has been configured to monitor the /var/log/apache2/access2.log file. As far as I know, this would result the same as executing the command /opt/splunkforwarder/bin/splunk add monitor -auth adminuser:adminpassword /path/to/logs, but I have gone directly into inputs.conf this time.

Additionally, source, sourcetype and index metadata is being configured in order to be assigned to the logs posteriorly.

Lastly, in this file it is indicated the group of indexers, named indexers.

![](../../../../splunkSiemImages/IMG4)

Now, file /opt/splunkforwarder/etc/system/local/outputs.conf which is also documented officially https://docs.splunk.com/Documentation/Splunk/9.4.0/Admin/Outputsconf

Here it is being configured to send by default all the data to the indexer group indexers.

The expected server to receive the data is declared in server, which is 127.0.0.1:9997, as opened previously. Lastly, tcpout-server is a parameter used by splunk to internally manage the connections and retries, pointing also to 127.0.0.1:9997



![](../../../../splunkSiemImages/IMG5)


With all this configuration done, I perform the steps:

1. Stop splunk: sudo /opt/splunk/bin/splunk stop
2. Restart splunk forwarder: sudo /opt/splunkforwarder/bin/splunk restart
3. Start splunk: sudo /opt/splunk/bin/splunk start

This is because restarting splunk forwarder with splunk initiated creates a conflict with the port 8089, and I figured out how to solve this issue this way on my first day using splunk.

Once all the configurations are done, in Splunk Search > Data Summary, the forwarder should be listed


![](../../../../splunkSiemImages/IMG6)

# Apache2

In this case I am using an apache2 server with a simple form representing a login page:

![](../../../../splunkSiemImages/IMG7)


This login page is intended to send insecurely the credentials through 2 get parameters for demonstration purposes: username, password

If I send some requests, this would be reflected in splunk at the moment, otherwise possible there is an issue with the forwarder configuration.

As configured, I will find the request by searching the hostname in this case, which I said it is ubuntu2404

![](../../../../splunkSiemImages/IMG8)

# The dashboard

In order to create a simple dashboard in splunk, I just create it through the user interface

![](../../../../splunkSiemImages/IMG9

In this case, it is named: SQLi dashboard
This is because it is intended to represent a dashboard that would only show SQLi attempts in the apache2 login page

![](../../../../splunkSiemImages/IMG10)

Once created, I select the tab and modify the event search, by crafting an SPL query in order to add a regex that will trigger when SQL words such as union, select, insert, drop, update, delete, exec; special characters such as --, #,;,/*,*/,... and hexadecimal values are detected within the request, just as common possible patterns of a SQLi attack. The query would result as seen below:


![](../../../../splunkSiemImages/IMG11)


So now if if I send a request that contains any of the specified characters, the it will be shown in this dashboard:

![](../../../../splunkSiemImages/IMG12)


Working harder on this dashboard may be helpful to detect in a web service possible SQLi attacks, among others, such as XSS, command injection, LDAP queries, etc. If this behavior is found in any system, it may be related to the MITRE ATT&CK technique T1190 as it is defined as an attempt to exploit a weakness in an Internet-facing host or system to initially access a network.

https://attack.mitre.org/techniques/T1190/

