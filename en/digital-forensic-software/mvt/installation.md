---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

### Install MVT On Linux

This guide explains how to setup and run Mobile Verification Toolkit or MVT on Ubuntu. Below installation steps assume that all the depency packages of MVT software are installed and up to date on your system. For Linux distributions, please follow the below installing mvt steps. First install basic dependencies that are necessary to build all required tools using command:

    sudo apt install python3 python3-pip libusb-1.0-0 sqlite3

If you want to only use mvt-ios and not mvt-android then libusb-1.0-0 package is not required. Next, install MVT on Linux. Add locally installed Pypi binaries to your $PATH in .bashrc or .zshrc file using command:

    export PATH=$PATH:~/.local/bin

Now you can install MVT directly from pypi by command:

    pip install mvt

Or from the source code clone:

    git clone https://github.com/mvt-project/mvt.git
    cd mvt
    pip3 install

That's it. You now should have the mvt-ios and mvt-android utilities installed.

Congratulations! You have successfully installed Mobile Verification Toolkit (MVT) on Linux. Enjoy!
