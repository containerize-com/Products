---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Seafile On Ubuntu**

This guide explains how to setup and run sea file server from a pre-built package with MySQL. Below installation steps assume that all the depency packages of Seafile cloud are installed and up to date on your system. Please follow seafile installation steps:

    sudo apt update
    sudo apt install python3 python3-{pip,pil,ldap,urllib3,setuptools,mysqldb,memcache,requests}
    sudo apt install libpython3.8 ffmpeg

Download the latest seafile server package from [seafile download](https://www.seafile.com/en/download/). At the time of this installation the latest release of seafile server is 8.0.5 64bit:

    sudo apt -y install wget
    wget https://download.seadrive.org/seafile-server_8.0.5_x86-64.tar.gz

Once the file download is completed, extract the archive to /opt directory:

    sudo tar -xvf  seafile-server_8.0.5_x86-64.tar.gz -C /opt
    sudo mv /opt/seafile-server-8.0.5 /opt/seafile

Next, just run setup script.

    cd /opt/seafile/
    sudo ./setup-seafile-mysql.sh

This script will guide you to setup your seafile server using MySQL. Seafile Server will run on port 8082 and the Seafile Web UI will be accessible on the port 8000. Now start Seafile services by:

    cd /opt/seafile
    sudo ./seafile.sh start

Next, start the Seahub Django website frontend service. 

    sudo ./seahub.sh start 

When you start Seahub, the script would prompt you to create an admin account for your Seafile Server account.

Port defaults to 127.0.0.1:8000. So, we recommend you to deploy a reverse proxy service so that other users can access the Seahub service. You can stop Seahub website and Seafile processes with:

    ./seahub.sh stop
    ./seafile.sh stop

Congratulations! You have successfully installed Seafile file sync and share platform on Ubuntu. Enjoy!
