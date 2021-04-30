---
title: Installation Guide
onpagelink: installation
weight: 3

---


#### **Installation Instructions**

Once pre-requisites are in place, open the command line and run and check dependencies are satisfied and various paths correctly set to find different libraries and include files.

Now, build `Makefile`:

    qmake PREFIX=/usr/local/

Compile `shotcut`:

    make -j8 

Then, run the following command:

    make install

Finally, run `shotcut` from a build folder without installing you can make a symbolic link to the `qml` folder. It depends on where you build folder is, but assuming it is a sibling of the source tree folder:

    cd buildmkdir -p share/shotcutcd share/shotcutln -s ../../../shotcut/src/qml

