---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions

#### **Install OpenEdx on Ubuntu 20.04**

First, update Ubuntu packages by running the following commands.

 ```
$ sudo apt-get update -y
$ sudo apt-get upgrade -y
$ sudo reboot
```

Run the command below to set the OPENEDX_RELEASE variable.

 ```
$ export OPENEDX_RELEASE=open-release/lilac.1
```

Create a config.yml file and specifies the hostname of the LMS & Studio.

 ```
EDXAPP_LMS_BASE: "online.myeducation.org"
EDXAPP_CMS_BASE: "studio.online.myeducation.org"
```

Run the following command for Ansible installation.

 ```
$ wget https://raw.githubusercontent.com/edx/configuration/$OPENEDX_RELEASE/util/install/ansible-bootstrap.sh -O - | sudo -E bash 
```

Generate randomize passwords and save my-passwords.yml file in a safe place

 ```
$ wget https://raw.githubusercontent.com/edx/configuration/$OPENEDX_RELEASE/util/install/generate-passwords.sh -O - | bash
```

Run the command below to install the OpenEdX. It would take time so you need to keep patience.

 ```
$ wget https://raw.githubusercontent.com/edx/configuration/$OPENEDX_RELEASE/util/install/native.sh -O - | bash
```