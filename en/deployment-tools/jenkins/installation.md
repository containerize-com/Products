---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing using Ubuntu

Add the repository key to the system.

 ```
wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
```

Run the following command to add repository to the list.

 ```
sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```

Run below command to update the repositories.

 ```
sudo apt update
```

Install Jenkins.

 ```
sudo apt install jenkins
```

Start Jenkins service.

 ```
sudo systemctl start jenkins
```

Open the site http://your\_server\_ip\_or\_domain:8080 and follow installation wizard.

#### **Explore**

You may find the following links relevant:

- [Top 5 Open Source Deployment Tools In 2021](https://blog.containerize.com/2021/03/12/top-5-open-source-deployment-tools-in-the-year-2021/)
- [Continuous Integration And Continuous Deployment From Source Control Server](https://blog.containerize.com/2021/02/22/automate-software-deployment-process-with-jenkins-and-github/)
 