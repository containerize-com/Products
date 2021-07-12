---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Once pre-requisites are installed, run the following command to create directory for the source code.:

    mkdir ~/blender-git
    cd ~/blender-git

Now, run the following command to clone the source code files:

    git clone https://git.blender.org/blender.git

After that, run the following commands:

    cd blender
    make update

Then, build Blender by running the following command in the terminal:

    cd ~/blender-git/blender
    make

Finally, upon a successful build, you can find Blender.app ready to run in ~/blender-git/build\_darwin/bin.

