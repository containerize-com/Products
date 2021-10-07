---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing on Linux

You can install Statping on Linux by downloading tar.gz file, unzipping, and running the executable Or you can simply run the install/upgrade script below.

 ```
curl -o- -L https://statping.com/install.sh | bash
```

#### Install using Snapcraft

You can simply run this command to install Statping.

 ```
sudo snap install statping
```

#### Installation using Docker

Pull Statping image from hub.docker.com

 ```
docker pull statping/statping
```

Use below command to run it on Docker

 ```
docker run -it -p 8080:8080 statping/statping
```
