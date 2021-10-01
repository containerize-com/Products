---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

Modoboa Installer is the easiest and the quickest way to set up a fully functional server (modoboa, postfix, dovecot, amavis and more) on one machine.

To use it, just run the following commands in your terminal:
```
$ git clone https://github.com/modoboa/modoboa-installer
$ cd modoboa-installer
$ sudo ./run.py <your domain>
```

if you get this warning - `‘/usr/bin/env: ‘python’: No such file or directory’`, do make sure sure python is installed on your server. Sometimes python is installed but the installer can’t detect it or which python version to run, especially on a debian based system. Then run this command first.

```
sudo apt-get install python-virtualenv python-pip
```

Wait a few minutes and you’re done
