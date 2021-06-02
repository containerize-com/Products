---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation Instructions**

This installation guide is for Windows. Once all the pre-requisites are installed, run the following command in the terminal to clone the source code:

    git clone https://github.com/panda3d/panda3d

It will most likely be in the C:\Documents and Settings\<your user name> folder.

    cd C:\panda_source

Now, run the following command:

    makepanda\makepanda.bat

After that, run the following command to compile the source code:

    makepanda\makepanda.bat --everything
    
Then, run the following command to make an installer, If you’ve used the .sln file to build Panda, and used “Release” mode, the installer .exe has already been created for you.

    makepanda\makepanda.bat --everything --installer

This should take much less time because if you notice there will be a “built” folder in your C:\panda_source, this was created in the previous step. 
