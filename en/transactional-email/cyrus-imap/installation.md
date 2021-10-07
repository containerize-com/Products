---
title: Installation Guide
onpagelink: installation
weight: 3

---
### **Installation**

The first place to start with a new installation of Cyrus IMAP is with your OS distribution of choice and their packaging, where available. In this tutorial, we’ll explain for CentOS Distribution.

To install the version of Cyrus IMAP that comes with the operating system, issue the following command:
```
$ yum install cyrus-imapd cyrus-sasl cyrus-sasl-plain
```

Next, set a password for the default administrative user “cyrus”
```
$ passwd cyru
Changing password for user cyrus.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.s
```

Start and configure to start when the system boots, the saslauthd service
```
$ service saslauthd start
Starting sasluathd:
$ chkconfig sasluathd on
```

You should now be able to authenticate against sasluathd:
```
$ testsaslauthd -u cyrus -p YOUR-PASSWORD
```

Start the service, and ensure the service starts up when the system boots:
```
$ service cyrus-imapd start
$ chkconfig cyrus-imapd on
```

You should now be able to login as the cyrus user
```
$ imtest -t "" -u cyrus -a cyrus localhost
S: * OK [CAPABILITY IMAP4 IMAP4rev1 LITERAL+ ID STARTTLS LOGINDISABLED COMPRESS=DEFLATE] d5ec35c1414a Cyrus IMAP v2.3.16-Fedora-RPM-2.3.16-13.el6_6 server ready
C: S01 STARTTLS
S: S01 OK Begin TLS negotiation now
verify error:num=18:self signed certificate
TLS connection established: TLSv1.2 with cipher DHE-RSA-AES256-GCM-SHA384 (256/256 bits)
C: C01 CAPABILITY
S: * CAPABILITY IMAP4 IMAP4rev1 LITERAL+ ID AUTH=PLAIN SASL-IR COMPRESS=DEFLATE ACL RIGHTS=kxte QUOTA MAILBOX-REFERRALS NAMESPACE UIDPLUS NO_ATOMIC_RENAME UNSELECT CHILDREN MULTIAPPEND BINARY SORT SORT=MODSEQ THREAD=ORDEREDSUBJECT THREAD=REFERENCES ANNOTATEMORE CATENATE CONDSTORE SCAN IDLE LISTEXT LIST-SUBSCRIBED X-NETSCAPE URLAUTH
S: C01 OK Completed
Please enter your password:
C: A01 AUTHENTICATE PLAIN ************
S: A01 OK [CAPABILITY IMAP4 IMAP4rev1 LITERAL+ ID LOGINDISABLED COMPRESS=DEFLATE ACL RIGHTS=kxte QUOTA MAILBOX-REFERRALS NAMESPACE UIDPLUS NO_ATOMIC_RENAME UNSELECT CHILDREN MULTIAPPEND BINARY SORT SORT=MODSEQ THREAD=ORDEREDSUBJECT THREAD=REFERENCES ANNOTATEMORE CATENATE CONDSTORE SCAN IDLE LISTEXT LIST-SUBSCRIBED X-NETSCAPE URLAUTH] Success (tls protection)
Authenticated.
Security strength factor: 256
. LIST "" "*"
. OK Completed (0.000 secs 1 calls)
C: Q01 LOGOUT
* BYE LOGOUT received
Q01 OK Completed
Connection closed.
```
