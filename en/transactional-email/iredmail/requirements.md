---
title: System Requirements
onpagelink: requirements
weight: 1

---

### System Requirements

- iRedMail is designed to be deployed on a FRESH server system, which means your server does NOT have mail related components installed, e.g. MySQL, OpenLDAP, Postfix, Dovecot, Amavisd, etc. iRedMail will install and configure them for you automatically. Otherwise it may override your existing files/configurations although it will backup files before modifying, and it may not be working as expected.
- Many ISPs block port 25 by default, it's used for communication between mail servers, it must be open, otherwise your server may be not able to receive or / and send emails. Please contact your ISP to make sure it's not blocked, or ask them to unblock. 
  - Amazon AWS EC2. Request to remove the throttle on port 25.
  - Google Cloud Platform.
  - Microsoft Azure.
  - Linode. Explained in the blog post, you can open a support ticket to request the Linode team to open it.
  - DigitalOcean. According to a post in their community, SEEMS impossible to unblock port 25, that means you can NOT run mail server on DigitalOcean VPS.
 