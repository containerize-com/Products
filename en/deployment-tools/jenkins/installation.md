---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installing using Ubuntu

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

