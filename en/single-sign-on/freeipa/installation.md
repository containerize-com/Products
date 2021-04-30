---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

First, run the following command to clone the source code:

    git clone https://pagure.io/freeipa.git

Next, install the packages on your system by running the following commands:

    cd freeipa
    cp freeipa.spec.in freeipa-builddep.spec 
    sudo yum-builddep freeipa-builddep.spec

After that, run the following command:

    sudo dnf copr enable @freeipa/freeipa-master

Once all the dependencies are installed, run the following command to make build:

    ./makerpms.sh
    sudo yum localinstall dist/rpms/*.rpm

In addition, if you have IPA installed on your development system you can do some limited in-tree development of management plugins. To do this:

Server setup:

*   As root user, install IPA using ipa-server-install
*   Create ~/.ipa/alias/.pwd and enter the admin password
*   Run kinit admin
*   To run the server, execute python lite-server.py

Client setup:

*   Copy /etc/ipa/default.conf into ~/.ipa/default.conf
*   Replace xmlrpc\_uri with [http://127.0.0.1:8888/ipa/xml](http://127.0.0.1:8888/ipa/xml)
*   To run the CLI, execute ./ipa <command>

Finally, FreeIPA will detect that it is running in-tree and will use the port and XML-RPC location that lite-server.py is listening only to. However, if you make changes to the server-side of a plugin you’ll need to restart lite-server.py.

