---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing on Ubuntu

Run command to add PPA to your system.

 ```
sudo add-apt-repository ppa:bzr/ppa
```

Run below command to update package repositories.

 ```
sudo apt-get update
```

Install Bazaar.

 ```
sudo apt-get install bzr
```

#### Installing on Fedora

Run command to install it on Fedora.

 ```
su -c 'yum install bzr'
```

### Installing on CentOS/RHEL

Enable EPEL repository, in case you have not enabled it.

 ```
su -c 'rpm -Uvh http://dl.fedoraproject.org/pub/epel/5/i386/epel-release-5-4.noarch.rpm'
```

Execute command.

 ```
su -c 'yum install bzr'
```

