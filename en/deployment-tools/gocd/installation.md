---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing using Ubuntu

Run below commands in order to install GoCD Server.

 ```

echo "deb https://download.gocd.org /" | sudo tee /etc/apt/sources.list.d/gocd.list
curl https://download.gocd.org/GOCD-GPG-KEY.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install go-server

```

Run below commands in order to install GoCD Agent.

 ```

echo "deb https://download.gocd.org /" | sudo tee /etc/apt/sources.list.d/gocd.list
curl https://download.gocd.org/GOCD-GPG-KEY.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install go-agent

```

#### **Explore**

You may find the following links relevant:

- [Top 5 Open Source Deployment Tools In 2021](https://blog.containerize.com/2021/03/12/top-5-open-source-deployment-tools-in-the-year-2021/)
- [Continuous Integration And Continuous Deployment From Source Control Server](https://blog.containerize.com/2021/02/22/automate-software-deployment-process-with-jenkins-and-github/)
- [Automate PHP Application Deployment With Deployer](https://blog.containerize.com/2021/03/05/automate-php-application-deployment-with-deployer/)
 