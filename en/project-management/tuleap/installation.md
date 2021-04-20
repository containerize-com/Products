---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

The full installation is the common way to install tuleap. It uses your distribution package system and will provide a fully configurable and adjustable environment. It is robust so you can deploy production environment this way.

Install EPEL You will need EPEL for some dependencies

 ```
yum install -y epel-release
 
```

If you use Red Hat, you will need to activate the Optional channel. Install the Software Collections repositories

On CentOS this is done by:

 ```
yum install centos-release-scl 
```

On RedHat this is done by:

 ```
yum-config-manager --enable rhel-server-rhscl-7-rpms 
```

Install remi-safe repository (needed for PHP dependencies):

 ```
yum install https://rpms.remirepo.net/enterprise/remi-release-7.rpm 
```

Install Tuleap repositories Create a /etc/yum.repos.d/Tuleap.repo with this conten

 ```
[Tuleap]
name=Tuleap
baseurl=https://ci.tuleap.net/yum/tuleap/rhel/7/dev/$basearch
enabled=1
gpgcheck=1
gpgkey=https://ci.tuleap.net/yum/tuleap/gpg.key
```

Install Tuleap by running the following command:

 ```
yum install -y \
  rh-mysql57-mysql-server \
  tuleap \
  tuleap-plugin-agiledashboard \
  tuleap-plugin-graphontrackers \
  tuleap-theme-burningparrot \
  tuleap-theme-flamingparrot \
  tuleap-plugin-git \
  tuleap-plugin-pullrequest 
```

Configure the database

Ensure that

 ```
 /etc/opt/rh/rh-mysql57/my.cnf.d/rh-mysql57-mysql-server.cnf 
```

contains

 ```
sql-mode=NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION 
```

in section \[mysqld\]

 ```
 # Add 'sql-mode' parameter after [mysqld]
sed -i '20 a sql-mode=NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION' /etc/opt/rh/rh-mysql57/my.cnf.d/rh-mysql57-mysql-server.cnf

# Activate mysql on boot
systemctl enable rh-mysql57-mysqld

# Start it
systemctl start rh-mysql57-mysqld

# Set a password
scl enable rh-mysql57 "mysqladmin -u root password"
 
```

### Setup

Please do not repeat this step twice. This script should only be executed once. If you have any errors in the previous steps, be sure to fix those before continuing.

As root, run:

 ```
/usr/share/tuleap/tools/setup.el7.sh \
  --configure \
  --server-name=FQDN \
  --mysql-server=localhost \
  --mysql-password=XXXXX
```

With:

- FQDN being the name of the server as you access it on your network (localhost for a local test, tuleap.example.com with a DNS entry 192.168.1.123 if you only have an IP address)
- XXXXX being the password of root password of the db configured earlier.
- Ensure the firewall is properly configured. Open needed ports: 
  - Web (TCP/80 &amp; TCP/443)
  - SSH (git, admin): TCP/22
 
### Mail configuration

Tuleap interacts with Postfix to process mails. The following lines should be uncommented/modified in the main Postfix configuration file generally located in /etc/postfix/main.cf:

 ```
myhostname = mytuleap.domainname.example.com
alias_maps = hash:/etc/aliases,hash:/etc/aliases.codendi
alias_database = hash:/etc/aliases,hash:/etc/aliases.codendi
recipient_delimiter = +
 
```

### First connection

Once these steps are completed, you can access the Tuleap server with the web interface. Go to your Tuleap domain name

Default site administrator credentials can be found in /root/.tuleap\_passwd. Store it securely and delete the file as soon as possible.