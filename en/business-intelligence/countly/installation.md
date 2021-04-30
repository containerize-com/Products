---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once the pre-requisites are installed, run the following command to download the source files:

    git clone https://github.com/Countly/countly-server.git

Extract the Countly package to the directory of your taste (e.g. under /usr) – **do not use the** /root folder for this purpose. Then, fire the easy installation script that comes with Countly, which will work for both Ubuntu and RHEL/CentOS:

    sudo su –cd COUNTLY_INSTALLATION_DIRECTORY/bin

Then, run the following command:

    bash countly.install.sh

Installation may take between 10-15 minutes. Finally, access your application into the browser at the following link:  

    http://your_server_ip_or_domain/

