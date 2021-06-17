---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

Run the following command to clone the repo of this free saml service provider:

    git clone --recursive  https://github.com/OpenIdentityPlatform/OpenAM.git

After a successful clone run the following command:

    mvn install -f OpenAM

Then, add FQDN host name in /etc/hosts (Windows c:\\windows\\systems32\\drivers\\etc\\hosts):

    127.0.0.1 login.domain.com

Run OpenAM with the following command:

    mvn cargo:run -f OpenAM/openam-server

The next step is then to go to [http://login.domain.com:8080/openam](https://href.li/?http://login.domain.com:8080/openam) where you’ll see the OpenAM welcome page. 

