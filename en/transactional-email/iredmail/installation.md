---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Preparations

##### Set a fully qualified domain name (FQDN) hostname on your server

No matter your server is a testing machine or production server, it's strongly recommended to set a fully qualified domain name (FQDN) hostname.

Enter command `hostname -f` to view the current hostname:

 ```
$ hostname -f
mx.example.com
```

On Debian/Ubuntu Linux, hostname is set in two files: `/etc/hostname` and `/etc/hosts`.

- `/etc/hostname`: short hostname, not FQDN. ```
  mx
  ```
- `/etc/hosts`: static table lookup for hostnames. Warning: Please list the FQDN hostname as first item. ```
  # Part of file: /etc/hosts
  127.0.0.1   mx.example.com mx localhost localhost.localdomain
  ```
  
   Verify the FQDN hostname. If it wasn't changed after updating above two files, please reboot server to make it work. ```
  $ hostname -f
  mx.example.com
  ```
 
##### Enable default official Debian/Ubuntu apt repositories

- iRedMail needs official Debian/Ubuntu apt repositories, please enable them in `/etc/apt/sources.list`.
- Install package `gzip` so that you can uncompress downloaded iRedMail package. ```
  # sudo apt-get install gzip
  ```
 
##### Download the latest release of iRedMail

- Visit Download page to get the latest stable release of iRedMail.
- Upload iRedMail to your mail server via ftp or scp or whatever method you can use, login to the server to install iRedMail. We assume you uploaded it to `/root/iRedMail-x.y.z.tar.gz` (replace x.y.z by the real version number).
- Uncompress iRedMail tarball:
 
 
 ```
# cd /root/
# tar zxf iRedMail-x.y.z.tar.gz
```

#### Start iRedMail installer

It's now ready to start iRedMail installer, it will ask you several simple questions, that's all required to setup a full-featured mail server.

 ```
# cd /root/iRedMail-x.y.z/
# bash iRedMail.sh
```

- Specify location to store all mailboxes. Default is `/var/vmail/`.
- Choose backend used to store mail accounts. You can manage mail accounts with iRedAdmin, our web-based iRedMail admin panel.
- If you choose to store mail accounts in OpenLDAP, iRedMail installer will ask to set the LDAP suffix.
- Add your first mail domain name.
- Set password of admin account of your first mail domain.
- Choose optional components.
 
In the end iRedMail installer will ask you to review and confirm to start installation. It will install and configure required packages automatically. Type `y` or `Y` and press `Enter` to start.