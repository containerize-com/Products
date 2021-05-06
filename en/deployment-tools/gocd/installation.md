---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installing using Ubuntu

Run below commands in order to install GoCD Server.

 ```

echo "deb https://download.gocd.org /" | sudo tee /etc/apt/sources.list.d/gocd.list
curl https://download.gocd.org/GOCD-GPG-KEY.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install go-server

```

Run below commands in order to install GoCD Agent.

 ```

echo "deb https://download.gocd.org /" | sudo tee /etc/apt/sources.list.d/gocd.list
curl https://download.gocd.org/GOCD-GPG-KEY.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install go-agent

```

