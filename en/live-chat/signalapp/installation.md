---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Signal on Linux (Debian-based)

Signal Desktop is an Electron application that links with Signal on Android or iOS. Below instructions only work for 64 bit Debian-based Linux distributions such as Ubuntu, Mint etc.

Install signal official public software signing key.

 ```
wget -O- https://updates.signal.org/desktop/apt/keys.asc |\
sudo apt-key add - 
```

Add signal repository to your list of repositories

 ```
echo "deb [arch=amd64] https://updates.signal.org/desktop/apt xenial main" |\
sudo tee -a /etc/apt/sources.list.d/signal-xenial.list 
```

Update your package database and install signal.

 ```
sudo apt install apt-transport-https && sudo apt update && sudo apt install signal-desktop 
```

To use the Signal desktop app, Signal must first be installed on your phone.

Congratulations! You have successfully installed Signal desktop application.