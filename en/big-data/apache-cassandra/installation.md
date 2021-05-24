---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### **Install Apache Cassandra on Ubuntu**

Add the repository to the sources list.

 ```
sudo sh -c 'echo "deb http://www.apache.org/dist/cassandra/debian 40x main" > /etc/apt/sources.list.d/cassandra.list'
```

Execute command to pull the public key.

 ```
wget -q -O - https://www.apache.org/dist/cassandra/KEYS | sudo apt-key add -
```

Update the repository package list.

 ```
sudo apt update
```

Run the below command to install Cassandra.

 ```
sudo apt install cassandra
```