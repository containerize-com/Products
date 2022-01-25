---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Volatility On Linux**

In this guide, we will describe how to install Volatility on Linux. It is really easy to install and configure Volatility on any LTS version of Ubuntu. Below installation steps assume that all the depency packages are installed and up to date on your operating system. Let’s get started. First of all, you can get the source code by either downloading a stable release or cloning from github using command:

git clone https://github.com/volatilityfoundation/volatility.git

Install a few packages/libraries as prerequisites on Volatility Linux with command: 

sudo apt-get install pcregrep libpcre++-dev python-dev -y

This git clone will create a volatility source code folder on your system and now run Volatility directory from there. If you have downloaded the zip or tar source code archive there are two ways to install the code:

1. Extract the archive and run setup.py. This will take care of copying files to the right locations on your disk. Running setup.py is only necessary if you want to importing the Volatility namespace from other Python scripts as a library.

2. Extract the archive to a directory of your choice. For using Volatility just do python /path/to/directory/vol.py. This is a cleaner method since no files are ever moved outside of your chosen directory. It makes easier to upgrade to new versions when they are released. Also, you can easily have multiple versions of Volatility installed in separate directories for example /home/me/vol2.0 and /home/me/vol2.1.

For the most comprehensive plugin support, you should install the following [libraries and packages](https://github.com/volatilityfoundation/volatility/wiki/Installation)

Congratulations! You have successfully installed Volatility on Linux. Enjoy!