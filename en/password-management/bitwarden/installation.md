---
title: Installation
onpagelink: installation
weight: 3

---

### **Installation**
------------

Follow these steps to Install Bitwarden on Ubuntu 20.04 LTS Focal Fossa:

- Run following apt commands to update system packages.
 
 ```
sudo apt update
sudo apt upgrade
```

- Run following command to install dependencies
 
 ```
sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

- Now install Bitwarden using its Docker container.
 
 ```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
```

- Run following command to add the Docker repository.
 
 ```
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

- Install Docker and Docker Compose using the following command.
 
 ```
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose
```

- Now run following curl command.
 
 ```
curl -Lso bitwarden.sh https://go.btwrdn.co/bw-sh
chmod +x bitwarden.sh
```

- Start installation with the following command.
 
 ```
./bitwarden.sh install
```

- After successful installation, start the Bitwarden service with the following command
 
 ```
./bitwarden.sh start
```

- Now, access the web interface using the URL http://your-server-ip. You should see the Bitwarden login screen.
 
