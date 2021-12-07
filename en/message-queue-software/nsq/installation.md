---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install NSQ on Ubuntu**

NSQ is best message broker and easy to get started realtime distributed messaging platform. First, ensure that all the depency packages of NSQ are installed and up to date on your system. NSQ all parameters are specified on the command line and compiled NSQ binaries have no runtime dependency. Below guide covers NSQ installation on Debian and Ubuntu including distributions based on them. The following below instructions will run a NSQ cluster on your local machine. NSQ uses go modules to produce reliable builds so use below commands for compiling and to setup NSQ:

git clone https://github.com/nsqio/nsq
cd nsq
make

There are three separate binaries nsqlookupd, nsqd and nsqadmin that need to be installed and running. So, in one shell, start nsqlookupd using:

nsqlookupd

In second shell of terminal, start nsqd using:

nsqd --lookupd-tcp-address=127.0.0.1:4160

You can also add --broadcast-address=127.0.0.1. 

Most of the debugging, analysis, and administration is done via nsqadmin. So, start nsqadmin in new shell by running:

nsqadmin --lookupd-http-address=127.0.0.1:4161

Next, publish an initial message using:

curl -d 'hello world 1' 'http://127.0.0.1:4151/pub?topic=test'

Start nsq_to_file in another shell with command:

nsq_to_file --topic=test --output-dir=/tmp --lookupd-http-address=127.0.0.1:4161

Finally, publish more messages to nsqd like:

curl -d 'hello world 2' 'http://127.0.0.1:4151/pub?topic=test'
curl -d 'hello world 3' 'http://127.0.0.1:4151/pub?topic=test'

For testing run command in terminal:

./test.sh

For realtime debugging and monitoring below command also works very well:

watch -n 0.5 "curl -s http://127.0.0.1:4151/stats"

Finally, in your favourite web browser open http://127.0.0.1:4171/ to verify and view the nsqadmin UI and see statistics. Please also check the contents of the log files (test.*.log) written into /tmp directory.

Congratulations! You have successfully installed NSQ on ubuntu system. Enjoy!
