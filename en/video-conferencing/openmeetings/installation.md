---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

## Install Apache OpenMeetings On Ubuntu

Before installing Java, first install all necessary prerequisites. The latest stable release of OpenMeetings is 4.0.10 at time of writing these instructions. Now we can start downloading OpenMeetings after installing dependency packages. Open a terminal session or connect to your server and run the below command. To do this I’ll go to the /tmp/ folder and from there with the help of the wget command start the OpenMeetings download:

    cd /tmp/
    wget http://www-eu.apache.org/dist/openmeetings/4.0.10/bin/apache-openmeetings-4.0.10.tar.gz

Decompress the downloaded file in openmeetings folder and then move openmeetings to /opt/ folder:

    mkdir openmeetings
    sudo tar xvf apache-openmeetings-4.0.10.tar.gz -C openmeetings/
    sudo mv openmeetings /opt/

Now access /opt/openmeetings and start the server:

    cd /opt/openmeetings
    sudo sh red5.sh openmeetings

Now you have to complete the installation from the web interface using your favorite web browser and visit the following address:

    http://your-server-ip:5080/openmeetings

Next, press the > button, select MariaDB or MySQL, create the admin user and group, set up settings and configuring by completing the installation steps. Next, log in to use the application.

Congratulations! You have now set up the OpenMeetings tool. Enjoy!

