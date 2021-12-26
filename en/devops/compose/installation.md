---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Portainer with Docker on Linux**

This document installation steps assume that all the depency packages of the community edition of Portainer are installed and up to date on your Linux environment. For Linux operating system setup, please follow the below installions steps to install the Portainer Server container. First, create the volume that Portainer Server will use to store its database using below command:

    docker volume create portainer_data

Next, download and install the Portainer best container management software by running below in terminal:

    docker run -d -p 8000:8000 -p 9443:9443 --name portainer \
        --restart=always \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -v portainer_data:/data \
        portainer/portainer-ce:latest

By default, Portainer container management system installation generates a self-signed SSL certificate to secure port 9443. If you need HTTP port 9000 open for legacy reasons then you can add the following in docker run command:

    -p 9000:9000

Now you can check to see whether the Portainer Server container has started by running docker ps commamd:

    docker ps

Optionally you can install the Portainer Agent alongside your Portainer Server installation and Docker standalone by runing the following command:

    docker run -d -p 9001:9001 --name portainer_agent --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/volumes:/var/lib/docker/volumes portainer/agent:latest

Portainer Agent provides additional functionality such as volume browsing from Portainer. Now, you can log into your Portainer Server instance by browsing url:

    https://localhost:9443

You need to replace localhost with the IP or Fully qualified domain name(FQDN) and you will see the initial setup page for Portainer Server. That's it, Portainer Server has been installed. Congratulations! You have successfully setup Portainer docker container management server on Linux. Enjoy!