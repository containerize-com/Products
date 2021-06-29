---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

### Install Pydio Cells On Ubuntu

There are many different ways to install cells enterprise file synchronization and sharing but here we will discuss installation steps for Ubuntu. Pydio Cells sharesync is easy to setup and get started. To get started with Pydio Cells quickly, configure and setup environment with the necessary dependencies packages. Assuming that your system meets the above prerequisites packages. Building the pydio cells efss backend from the source code is simple and quite straight forward. After getting database access information and login as non-root user, get the source code:

    go get -u github.com/pydio/cells

If If you need to install the Enterprise Edition efss, then use wget command to get Pydio binary. From this line on, we assume you are in Pydio Cells' source code roots directory

    cd $GOPATH/src/github.com/pydio/cells

Next, build your binary

    make dev

After Download the binary for your server architecture, you can make it executable by:

    chmod +x ./cells

Run the pydio open source installer that will guide you through the necessary steps and run:

    ./cells configure

If cells web installer does not restarts automatically then use:

    ./cells start

If your machine is local or web accessible, a temporary web server will start on TCP port [:8080]. It will provide a wizard for configuring basic settings. Open your favourtie web browser at https://localhost:8080 or https://[server ip or domain]:8080).

Congratulations! You have now set up the pydio cells open source file sharing platform. Enjoy!
