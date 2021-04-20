---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using DEB/RPM packages

Import the PGP key used to sign our packages:

 ```
<pre class="command">```
wget -qO- https://dl.packager.io/srv/opf/openproject/key | sudo apt-key add -

```
```

Add the OpenProject package source:

 ```
<pre class="command">```
sudo wget -O /etc/apt/sources.list.d/openproject.list \
  https://dl.packager.io/srv/opf/openproject/stable/10/installer/ubuntu/20.04.repo

```
```

Download the OpenProject package:

 ```
<pre class="command">```
sudo apt-get update
sudo apt-get install openproject

```
```

To start the configuration wizard, please run the following command with sudo, or as root:

 ```
<pre class="command">```
sudo openproject configure

```
```

Follow the configuration wizard steps and you have your OpenProject website ready to use.