---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation Instructions**

Once you have installed the Docker, run the following command to pull the Docker image:

    docker pull jbuchbinder/freemed

Now, run the following commands to spin up the Docker container:

    docker build -rm -t freemed git://github.com/freemed/freemed-docker.git
    docker run -p 8080:80 -d freemed

Finally, you can access the application in the browser using the following address:

    http://localhost:8080/

