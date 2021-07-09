---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

### Install Ceph On Ubuntu

This guide explains how to setup and run Ceph on Ubuntu. Below installation steps assume that all the depency packages of Ceph software defined storage solution are installed and up to date on your system. For Debian and Ubuntu distributions, please follow the below installing ceph steps. First, add the release key:

    wget -q -O- 'https://download.ceph.com/keys/release.asc' | sudo apt-key add -

Next, add the Ceph packages to your repository. Use the command below and replace {ceph-stable-release} with a stable Ceph release like:

    echo deb https://download.ceph.com/debian-{ceph-stable-release}/ $(lsb_release -sc) main | sudo tee /etc/apt/sources.list.d/ceph.list

Update your repository and install ceph-deploy:

    sudo apt update
    sudo apt install ceph-deploy

To clone the Ceph source code repository, run command:

    git clone --recursive https://github.com/ceph/ceph.git
    cd ceph

Once git clone is completed, you should have a full copy of the Ceph code repository. Ceph contains many git submodules that need to be checked out with command:

    git submodule update --init --recursive

Before you can build Ceph source code, you need to install several libraries and tools by:

    ./install-deps.sh

Ceph sds storage is built using cmake. To build Ceph, navigate to your cloned Ceph repository and execute the following command:

    cd ceph
    ./do_cmake.sh
    cd build
    ninja

To build a complete source tarball with everything needed and to build from source, build a deb or rpm package:

    ./make-dist

That's it. Congratulations! You have successfully installed deployed Ceph storage cluster on Ubuntu. Enjoy!