---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Kubernetes on Linux**

Below installation steps assume that all the depency packages of Kubernetes are installed and up to date on your system. For Linux distributions setup, please follow the below installing steps. There are two options to build Kubernetes right away. It is possible to build Kubernetes using a local golang installation and there is also a build process that runs in a Docker container. Kubernetes development helper scripts require an up to date GNU development tools environment with commands:

    sudo apt update
    sudo apt install build-essential

Docker environment option simplifies initial set up and provides a very consistent build and test environment. After installing basic dependencies, If You have a working Go environment then use below commands:

    mkdir -p $GOPATH/src/k8s.io
    cd $GOPATH/src/k8s.io
    git clone https://github.com/kubernetes/kubernetes
    cd kubernetes
    make

If you have a working Docker environment then run the following commands:

    git clone https://github.com/kubernetes/kubernetes
    cd kubernetes
    make quick-release

To build the entire Kubernetes project, run verification tests and pass unit tests, use the below command:

    make all
    make verify
    make test

That's it. Congratulations! You have successfully setup kubernetes for building k8s orchestration. Enjoy!