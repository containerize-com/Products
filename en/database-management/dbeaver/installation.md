---
title: Installation
onpagelink: installation
weight: 3

---

### **Installation**
------------

Here are the complete installation instruction for Ubuntu. Update system using following commands

Update system using following commands

 ```
sudo apt update
sudo apt upgrade
```

Then add Java repository

 ```
add-apt-repository ppa:linuxuprising/java
```

Now install Java11

 ```
apt-get update -y
apt-get install oracle-java11-installer -y
```

Check version

 ```
java -version
```

After that, add the DBeaver repository to your Ubuntu 18.04 instance. So first, download and add the GPG key for DBeaver

 ```
wget -O - https://dbeaver.io/debs/dbeaver.gpg.key | apt-key add -
```

Then add the DBeaver repository

 ```
echo "deb https://dbeaver.io/debs/dbeaver-ce /" | tee /etc/apt/sources.list.d/dbeaver.list
```

Finally install DBeaver CE

 ```
apt-get update -y
apt-get install dbeaver-ce -y
```

Check dbeaver version

 ```
apt policy dbeaver-ce
```

DBeaver is now installed. Access it from Unity dash. Open DBeaver workbench as follows:

 ![DBeaver | Open Source Database Management Software](/images/Dbeaver-screenshot.jpg "DBeaver | Open Source Database Management Software")
