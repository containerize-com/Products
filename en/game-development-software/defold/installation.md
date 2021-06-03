---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation Instructions**

Once all the pre-requisites are installed, run the following command in the terminal to clone the source code:

    git clone https://github.com/defold/defold.git

After that, run the following command to get into the root directory:

    cd defold

Then, run the commands to set up the environment:

    python2 ./scripts/build.py shell
    python2 ./scripts/build.py install_ext

After that, run the following commands to build with pre-built engine binaries suitable for your editor version:

    cd editor
    lein init archived-stable

Finally, start the editor with the following command:

    lein run
