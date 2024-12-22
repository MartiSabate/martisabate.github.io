---
layout: post
section-type: post
title: Stop opening malicious emails!
category: Category
tags: [ "cybersecurity" ]
---

It has happened to many of us, whether we realize it or not, that the emails we receive could not come from where we really think they are.

For example: If you received an email indicating that you must renew your Gmail account password, otherwise you will not be able to access it. Would you click on the link that supposedly redirects you to a website to change your current password?

This is a case that an unbelievable number of people would fall for, being unaware of what are the appropriate precautions to take into account when receiving unexpected emails.

The job of companies is to ensure that their original domain cannot be impersonated, with a correct implementation of SPF, DKIM and DMARC. Despite these measures, using a different domain, or other techniques, phishing attacks are still a risk today for everyone.

It must be understood that the objectives of a phishing attack are normally to open a malicious file or to give away sensitive data, such as personal data, banking data, etc.

This is the complete post from my Linkedin, where I want to share with you how to be prepared for when the time comes to check if the person sending you the email is a legitimate sender, or a possible scammer:

1. Use an antispam filter: an antispam filter is nothing more than a tool that identifies and blocks unwanted or malicious emails before they reach your inbox, thus eliminating the risk of you taking the actions that the attacker wants. In Gmail, you can configure that emails that have a dubious origin related to a specific domain are automatically classified as spam by the filters, and thus never appear in the inbox. This system not only works on a personal level, but also extends to other Gmail accounts that receive emails from a specific domain. Additionally, you can check the reputation of a specific domain with tools such as checking domains that are part of blacklists in web tools such as mxtoolbox https://mxtoolbox.com/blacklists.aspx

2. Take into account the headers: if you are suspicious of the email you have received, look at the headers, where, among other information, you can see the sender of the email. I would take this point into account especially when looking at the domain of the email sender, allowing us to detect if a possible attacker uses a domain similar to that of the company to try to impersonate it (for example faceboook.com). Checking this in all emails can be inefficient, and even useless if there is no problem in most emails, since a manual review of each one is exhausting on a daily basis. As a possible solution to domain impersonation attempts using this technique, you can use Gmail's "Labels" feature along with a filter so that every time you receive an email from a sender known for that domain, it will be automatically labeled by Gmail. In this way, domains that do not correspond to the sender of the email will not be labeled, and therefore suspicious. For example, filter emails from a domain by "*@domain.com", and assign them a label with a specific color.

5. Generic texts: this is a possible indicator of Phishing in unexpected emails, for example, if an email addresses you as "dear customer", or "dear user"; and does not mention your name, or anything that refers to you, and also asks you to make a bank transaction, or give your data, it is surely a phishing attack.

6. Lack of consistency in the sender's data: When the sender appears with a name that does not correspond to the email address, for example "John", associated with an email address "carl@domain.com", the sender has a very high probability of not being who he claims to be.

7. Suspicious URLs: although many URLs sent are highlighted in blue, these can be faked. That is, a fake URL can be superimposed to cover a fake one. To know which website you are going to visit before clicking, there are several things you can do:
7.1. Hover your mouse over it to analyze which URL it wants to send you to. If the address is not familiar to you, I suggest you use this online tool Site-Shot https://www.site-shot.com/, which is used to make an image of the page you are going to visit, without accessing it yourself.

8. Attachments: If the email contains an unexpected attachment, the best thing you can do is not open or download it. In case you need to know if it is safe to take the step, uploading the file to VirusTotal https://www.virustotal.com/gui/ is my highest recommendation for this type of occasion, and drawing a conclusion as to whether it is safe to run or not, based on the reliability of the sender seen in the previous suggestions. Despite not being suspicious, I would suggest opening the file in a virtual machine isolated from your network, avoiding both the risk of infecting your network and the risk of infecting your computer.

9. Urgent or alarming language: if the email content is requesting you to take some actions in priority or urgency, I would highly recommend taking all the security considerations before giving away sensitive information, or taking the requested action. This is a usual technique that attackers use in order to avoid the victim to think about the possible risks before taking action.

10. Spelling and grammar mistakes: this is common on non English speakers, who use a traductor, or do not understand the language at all, leading to possible unprofessional spelling mistakes.

11. Too good to be true offers: this technique is very old, like the nigerian letter. This consists on a payment request that would supposedly allow the sender make a transaction, or retire money from an ATM.

12. Lack of company branding: in some cases, senders attempt impersonate a big company, such as Google, Apple or Microsoft; however, in their emails the official branding structure is not being reflected. This is an indicator that the email is possibly not from the company they are saying to be.

13. No signatures or contact information: as malicious senders are willing to stay anonymous during all the process, from sending the email to getting sensitive data, or actions made by the victim; it is possible that in some cases they do not even a fake signature at the very end of the email. When a "very important" message doesn't have any signature, the most possible reason is because it is a phishing message.
