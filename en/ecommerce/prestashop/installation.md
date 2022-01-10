---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Installing on Ubuntu**

Run below command to install Nginx web server.

 ```
 sudo apt install nginx 
```

Run command to install and secure MySQL database server.

 ```
 sudo apt-get update;  sudo apt-get install mysql-server; mysql_secure_installation 
```

Install PHP for processing.

 ```
 sudo apt-get install php-fpm php-mysql
```

Now, you have installed all the required software and the next step is to login to mysql server and create prestashop database. Use following command to create database. Change with your database name.

 ```
 CREATE DATABASE prestashop; 
```

Create a database user called "prestashop" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER 'prestashopuser'@'localhost' IDENTIFIED BY 'new_password_here'; 
 GRANT ALL ON prestashop.* TO 'prestashopuser'@'localhost' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Download PrestaShop..

 ```
 
cd /tmp
wget https://download.prestashop.com/download/releases/prestashop_1.7.6.5.zip

```

Create directory for PrestaShop.

 ```
sudo mkdir -p /var/www/prestashop
```

Unzip downloaded file.

 ```
sudo unzip prestashop.zip -d /var/www/prestashop
```

Run below commands to set correct permission for www-data user.

 ```

sudo chown -R www-data:www-data /var/www/prestashop/
sudo chmod -R 755 /var/www/prestashop/

```

Create PrestaShop configuration file at Nginx so it can server the site.

Open site in browser and follow the installation wizard.

Congrats! You have successfully installed PrestaShop.

