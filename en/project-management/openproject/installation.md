---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation**

#### Installation using DEB/RPM packages

Import the PGP key used to sign our packages:

    wget -qO- https://dl.packager.io/srv/opf/openproject/key | sudo apt-key add -


Add the OpenProject package source:

    sudo wget -O /etc/apt/sources.list.d/openproject.list \
      https://dl.packager.io/srv/opf/openproject/stable/10/installer/ubuntu/20.04.repo


Download the OpenProject package:

    sudo apt-get update
    sudo apt-get install openproject


To start the configuration wizard, please run the following command with sudo, or as root:

    sudo openproject configure


Follow the configuration wizard steps and you have your OpenProject website ready to use.
