---
title: Installation Guide
onpagelink: installation
weight: 3

---


#### **Installation Instructions**

Once pre-requisites are in place, open the command line and run the following command to clone the source code:

    git clone https://gitlab.gnome.org/aleb/cerbero-pitivi.git 

After that, run the following command:

    /cerbero-uninstalled bootstrap

Now, start the build by running the following commands:

    cd cerbero-pitivi 
    ./cerbero-uninstalled build pitivi

Finally, run this command to start this open source video editor tool:

    ./build/dist/darwin_x86_64/bin/pitivi

