---
title: Features
onpagelink: features
weight: 2

---

### **Features**

This is a list of features (in no real particular order) of things that Postal can do.

#### General features

- Support for multiple organizations with mail servers &amp; users within.
- Graphs and stats showing volume of incoming &amp; outgoing mail.
- Access to view historical messages.
- Access to view the full outgoing &amp; incoming message queue.
- Set up webhooks to receive live information about delivery information in realtime. Full access to the last 7 days of webhook requests are also stored for debugging purposes.
- Built-in DNS checking &amp; monitoring to ensure domains you send mail from are configured correctly for maximum deliverability.
- Per server retention configuration to set how long messages should be kept in the database and the maximum size to keep on disk.
- Complete logging so delivery issues can easily be identified.
- Mail server wide search tools to find messages that need investigation.
 
#### Outgoing e-mails

- Send messages to the SMTP server or using the HTTP API.
- Manage multiple credentials per server.
- Support for DKIM signing of outbound messages.
- Enable development to hold messages in Postal without actually delivering them to recipients (message can be viewed in the Postal interface).
- Built-in suppression list to avoid sending mail to recipients that don't exist or can't accept e-mail.
- Click and open tracking to keep track of when recipients open your e-mails and click links within them.
- Configure per-server send limits to avoid abuse on mail servers.
- Management of multiple pools of sending IP addresses.
- Configure different senders or recipients to have mail delivered from certain IP addresses.
- Mail tagging so certain e-mails can be given a tag to allow them to be grouped when needed. For example, you may tag receipts or password-reset e-mails as such.
 
#### Incoming e-mails

- Ability to forward incoming e-mail to HTTP endpoints.
- Ability to forward incoming e-mail to other SMTP servers.
- Ability to forward incoming e-mail to other e-mail addresses.
- Spam &amp; thread checking with SpamAssassin and ClamAV with configurable thresholds and different methods for dealing with spam messages.
 
