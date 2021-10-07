---
title: Features
onpagelink: features
weight: 2

---

### **Features**

Exim supports all the modern features that you can imagine from top open source mail transfer agent software. These are some of the main features of Exim:

- Exim follows the same general approach of decentralized control that Smail does. There is no central process doing overall management of mail delivery. However, unlike Smail, the independent delivery processes share data in the form of `hints', which makes delivery more efficient in some cases. The hints are kept in a number of DBM files. If any of these files are lost, the only effect is to change the pattern of delivery attempts and retries.
- Many configuration options can be given as expansion strings, which are transformed in various ways when they are used. As these can include file lookups, much of Exim's operation can be made table-driven if desired. For example, it is possible to do local delivery on a machine on which the users do not have accounts. The ultimate flexibility can be obtained (at a price) by running a Perl interpreter while expanding a string.
- Access to view historical messages.
- Access to view the full outgoing &amp; incoming message queue.
- Exim has flexible retry algorithms, applicable to directing and routing addresses as well as to delivery.
- Exim contains header and envelope rewriting facilities.
- Unqualified addresses are accepted only from specified hosts or networks.
- Exim can perform multiple deliveries down the same SMTP channel after deliveries have been delayed.
- Exim can be configured to do local deliveries immediately but to leave remote (SMTP) deliveries until the message is picked up by a queue-runner process. This increases the likelihood of multiple messages being sent down a single SMTP connection.
- Remote deliveries of the same message to different hosts can optionally be done in parallel.
- Incoming SMTP messages start delivery as soon as they are received, without waiting for the SMTP call to close.
- Exim has support for the SMTP AUTH extension for authenticating clients, and for the STARTTLS extension for setting up encrypted connections.
- Perl-compatible regular expressions are available in a number of configuration parameters.
- Domain lists can include file lookups, making it possible to support very large numbers of local domains.
- Exim supports optional checking of incoming return path (sender) and receiver addresses as they are received by SMTP.
- SMTP calls from specific machines, optionally from specific idents, can be locked out, and incoming SMTP messages from specific senders can also be locked out. Exim also supports the use of the Realtime Blocking List (RBL).
- Hosts that are permitted to relay mail through a machine to another external domain can be controlled by IP number or IP network number. Relay control by recipient domain and sender address is also available.
- Messages on the queue can be `frozen' and `thawed' by the administrator.
- Exim can handle a number of independent local domains on the same machine; each domain can have its own alias files, etc. This facility is sometimes known as `virtual domains'.
- Simple mailing lists can be handled directly by Exim itself (but for `serious' mailing list operations, it is best to use it in conjunction with specialist mailing list software).
- Exim stats a user's home directory before looking for a `.forward' file, in order to detect the case of a missing NFS mount. Delivery is delayed if the directory is unavailable.
- Exim contains an optional built-in mail filtering facility. This can be configured to allow users to provide personal filter files, and it is also possible for a system-wide filter file to be applied to every message.
- There is support for multiple user mailboxes controlled by prefixes or suffixes on the user name, either via the filter mechanism or through multiple `.forward' files.
- Periodic warnings are automatically sent to messages' senders when delivery is delayed -- the time between warnings is configurable. The warnings can be made conditional on the contents of the message.
- A queue run can be manually started to deliver just a particular portion of the queue, or those messages with a recipient whose address contains a given string. There is support for the ETRN command in SMTP to interface to this.
- Exim can be configured to run as root all the time, except when performing local deliveries, which it always does in a separate process under an appropriate uid and gid. Alternatively, it can be configured to run as root only when needed; in particular, it need not run as root when receiving incoming messages or when sending out messages over SMTP. See chapter 55 for a discussion of security issues.
- I have tried to make the wording of delivery failure messages clearer and simpler, for the benefit of those less-experienced people who are now using email. Alternative wording for these messages can be provided in a separate file.
- The Exim Monitor is an optional extra; it displays information about Exim's processing in an X window, and an administrator can perform a number of control actions from the window interface. However, all such actions are also available from the command line interface.
 
