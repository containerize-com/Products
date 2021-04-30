---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Installing on Ubuntu**

Install Lighttpd web server using following command

    $ sudo apt install lighttpd

To test installation, go to your website or IP address

![Secure, Flexible And Lightweight Web Server](/images/Lighttpd_-_Check_status_on_browser.png "Secure, Flexible And Lightweight Web Server")

#### **Installing from source**

Download a release from www.lighttpd.net/download.

Use following commands to install via git

    git clone https://git.lighttpd.net/lighttpd/lighttpd1.4.git
    cd lighttpd1.4
    ./autogen.sh
    

Use these commands if you want to install via svn

    svn checkout https://github.com/lighttpd/lighttpd1.4/trunk lighttpd1.4

Fetch updates

    svn update

To install dependencies, run this command

    apt-get build-dep lighttpd

Configure

    ./configure --help

Build using make command

    make

After a successful build, now install the package

    su make install

