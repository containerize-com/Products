---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Compose with Docker on Linux**

This document installation steps assume that all the depency packages of the community edition of Compose are installed and up to date on your Linux environment. For Linux operating system setup, please follow the below installions steps to install the Compose Server container. First, create the volume that Compose Server will use to store its database using below command:

    docker volume create portainer_data

Next, download and install the Portainer best container management software by running below in terminal:

    docker run -d -p 8000:8000 -p 9443:9443 --name portainer \
        --restart=always \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -v portainer_data:/data \
        portainer/portainer-ce:latest

By default, Compose container management system installation generates a self-signed SSL certificate to secure port 9443. If you need HTTP port 9000 open for legacy reasons then you can add the following in docker run command:

    -p 9000:9000

Now you can check to see whether the Compose Server container has started by running docker ps commamd:

    docker ps

Optionally you can install the Compose Agent alongside your Compose Server installation and Docker standalone by runing the following command:

    docker run -d -p 9001:9001 --name portainer_agent --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/volumes:/var/lib/docker/volumes portainer/agent:latest

Compose Agent provides additional functionality such as volume browsing from Compose. Now, you can log into your Compose Server instance by browsing url:

    https://localhost:9443

You need to replace localhost with the IP or Fully qualified domain name(FQDN) and you will see the initial setup page for Compose Server. That's it, Compose Server has been installed. Congratulations! You have successfully setup Compose docker container management server on Linux. Enjoy!