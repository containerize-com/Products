---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installing using Snap store on Ubuntu

Snap is already installed, if you are running Ubuntu 16.04 or above. However, you can install it on Ubuntu 14.04 with below command.

 ```
$ sudo apt install snapd
```

Run the following command to install TDengine.

 ```
$ sudo snap install tdengine
```

#### Installing on Ubuntu

Download **TDengine-server-2.1.1.0-Linux-x64.deb** file from https://www.taosdata.com/en/getting-started/.

Run the following commands to install the TDengine:

 ```
$ sudo dpkg -i TDengine-server-2.1.1.0-Linux-x64.deb
$ sudo apt-get install -f
```

Start the TDengine service.

 ```
$ sudo systemctl start taosd
```

Command to launch TDengine shell.

 ```
$ taos
```