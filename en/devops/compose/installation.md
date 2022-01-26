---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Docker Compose On Linux**

First, ensure that all the depency packages of the Docker Compose are installed and up to date then please follow the instructions listed below. You can also download the Docker Compose binary from the Compose repository release page on GitHub for on linux. The step-by-step instructions are listed below. Run this command to download the current stable release of Docker Compose:

    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

To install a different version of Docker Compose linux, replace 1.29.2 with the version of Compose you want to install. Now, apply executable permissions to the downloaded binary:

    sudo chmod +x /usr/local/bin/docker-compose

If the command docker-compose fails after installation steps then check your paths. You can also create a symbolic link to /usr/bin or any other directory in your path with command:

    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

Optionally, you should install command completion for the bash and zsh shell. Now, test the installation using command:

    docker-compose --version

Congratulations! Now, you have learned how to install docker compose ubuntu 20.04 successfully. Enjoy!