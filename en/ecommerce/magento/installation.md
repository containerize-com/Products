---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Magento on Ubuntu 18.04 LTS with Nginx**

Run command to install Nginx web server.

 ```
 sudo apt install nginx 
```

Run below command to install MySql server.

 ```
 sudo apt-get install mysql-server
```

Secure MySql server.

 ```
 sudo mysql_secure_installation
```

You need to answers of few questions to secure MySQL database server.

Add third party repository to install PHP 7.1

 ```
 
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php

```

Execute command to update packages.

 ```
 sudo apt update  
```

Install PHP7.1-FPM and dependent modules.

 ```
 
sudo apt install php7.1-fpm php7.1-common php7.1-mbstring php7.1-xmlrpc php7.1-soap php7.1-gd php7.1-xml php7.1-intl php7.1-mysql php7.1-cli php7.1-mcrypt php7.1-ldap php7.1-zip php7.1-curl

```

Connect to MySQL server. Enter password when prompt.

 ```
 sudo mysql -u root -p
```

Create database by running the below command and then exit from MySQL.

 ```
 CREATE DATABASE magento;
```

Download latest release of Magento from: https://magento.com/tech-resources/download

Create directory for Magento.

 ```
 sudo mkdir /var/www/html/magento/
```

Extract downloaded Magento directory into /var/www/html/magento.

Set the correct permissions for Magento.

 ```

sudo chown -R www-data:www-data /var/www/html/magento/
sudo chmod -R 755 /var/www/html/magento/

```

Create Nginx configuration file for Magento and changes settings as per your environment.

Open your site in browser and follow the installation wizard.

