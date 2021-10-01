---
title: WildDuck | A free modern cross-platform open-source email server
description: WildDuck is a free, open-source email server for Microsoft Windows, Mac, Linux, or any OS that supports Node.js, MongoDB, and Redis. WildDuck supports Unicode.
keywords: open source email server, email server, spam protection, email server for All Platforms, free mail server, node.js, mongodb
singlepageh1title: A Self Hosted Open Source Email Server for All Platforms
singlepageh2title: WildDuck Mail Server is an open-source email server for large setups with a built-in REST API. WildDuck supports the most common protocols (IMAP, SMTP, POP3)
Shortdescriptionlistingpage: WildDuck is a self hosted on premise Mail Delivery Software. Use WildDuck when you have a large number of email accounts with large quotas.
linktitle: WildDuck
Imagetext:  Transactional Email Service
draft: false
weight: 8
layout: "single"
GithubLink: https://github.com/nodemailer/wildduck

HomePage_TitleText: Open Source Email Delivery Platform in JavaScript

ListingPage_MenuImage_TitleText: 
ListingPage_MenuImage_AltText: Cuttlefish is an alternative to Sendgrid and Mailgun.
ListingPage_Link_TitleText: 

SinglePage_HeaderImage_TitleText: 
SinglePage_HeaderImage_AltText: WildDuck is a free, open-source email server.
SinglePage_MenuImage_TitleText: 
SinglePage_MenuImage_AltText: WildDuck is a free, open-source email server.

---
### Overview

WildDuck Mail Server is a 100% free and open-source email server for Microsoft Windows, Mac, Linux, or any OS that supports Node.js, MongoDB, and Redis. The application is developed in Node.js, which is known for its speed. Source code is available on Github and you can extend the features by cloning the repository.

You should only consider using WildDuck if you have a large number of email accounts (1000+) with large quotas as WildDuck is designed to scale horizontally. For a smaller setup where everything fits into a single server, you might want to use something proven like an industry-standard Postfix+Dovecot setup instead.

It supports the most common email protocols like IMAP, SMTP, and POP3. It doesn’t use a file system to store email messages instead, everything is stored inside MongoDB. WildDuck is based on a serverless architecture which means all the instances are stateless which increases the throughput.  just add more WildDuck application servers behind a TCP load balancer, no need to worry about how to send specific users to specific mail servers.

The biggest advantage of WildDuck Mail Server is its high security. It doesn’t require root privileges, it does not touch the file system, no shell command. WildDuck supports Application Specific Passwords and multi-factor authentication which makes it a very secure and trusted system. Everything can be controlled by REST API, no need to modify config files. 
WildDuck provides all of the important functionality any business needs to run its own e-mail server. If you are looking to set up your own email server, then you should definitely check WildDuck Mail Server.
