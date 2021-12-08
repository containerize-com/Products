---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Wireshark On Ubuntu**

In this turotial, we will demonstrate how to install Wireshark on Ubuntu 20.04. It is really easy to install and configure Wireshark on any LTS version of Ubuntu. Below installation steps assume that all the depency packages are installed and up to date on your system. Let’s get started. First of all, update and upgrade your APT using the following commands. Open a terminal and use the following commands one by one:

    sudo add-apt-repository ppa:wireshark-dev/stable
    sudo apt update
    sudo apt upgrade

Now that Wireshark’s latest version has been added to the APT. You can download and install it with the following command:

    sudo apt install wireshark

When Wireshark network analyzer installs on your system, it requires superuser or root privileges to operate. Press the “Yes” button to allow other users, or press the “No” button to restrict others from using Wireshark. You can runn Wireshark without sudo by executing the following command:

    sudo dpkq-reconfigure wireshark-common

Select the “Yes” button to change the configuration settings to allow other users access to Wireshark. You must add a username to the Wireshark group so that this user can use Wireshark. To do this, execute the following command, adding your required username after “wireshark” in the command.

    sudo usermod -aG wireshark yasir

Next, launch Wireshark by typing the following command in the terminal window to start the Wireshark application:

    wireshark

You can also open Wireshark through the Graphical User Interface (GUI) on the Ubuntu desktop. Type 'Wireshark' in the search bar and click on the application. That's it.

Congratulations! You have successfully installed Wireshark on Ubuntu. Enjoy!