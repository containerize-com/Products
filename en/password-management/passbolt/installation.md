---
title: Installation
onpagelink: installation
weight: 3

---

Installation
------------

Follow these steps to Install Passbolt on Ubuntu server:

- If you are using ubuntu server image make sure the universe repository is present:
 
 ```
sudo add-apt-repository universe
sudo apt-get update
```

- The script will take care of installing all the services required by passbolt. It will ask you a few questions in order to adapt the environment to your needs.
 
 ```
wget -O passbolt-ce-installer-ubuntu-18.04.tar.gz https://www.passbolt.com/ce/download/installers/ubuntu/latest
wget -O passbolt-installer-checksum https://www.passbolt.com/ce/download/installers/ubuntu/latest-checksum
sha512sum -c passbolt-installer-checksum
tar -xzf passbolt-ce-installer-ubuntu-18.04.tar.gz
sudo ./passbolt_ce_ubuntu_installer.sh
```

- Lets first install MariDB database. Type 1 and hit Enter.
- Next you will have to set a password for the root database user and then create a new database user for Passbolt.
- On next screen type 1 and hit Enter to install Haveged.
- After that, enter hostname of ip address.
- Installation will start at this point.
- After a few minutes it will ask you to access Passbolt via web broswer.
- Point to Passbolt using IP address or hostname and complete the installation using web-based installation tool.
 