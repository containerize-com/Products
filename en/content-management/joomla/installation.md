---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

### Install Joomla CMS on Ubuntu 16.04 LTS with Nginx

Nginx is the most popular and secure web server. In order to install Nginx, use the following command

 ```
 sudo apt install nginx 
```

Once the Nginx is install, configure the domain and restart the Nginx by using the following command

 ```
 sudo service nginx restart 
```

Next, need to install database Server, use the following command to install MySql server

 ```
 sudo apt-get update;  sudo apt-get install mysql-server; mysql_secure_installation 
```

Once, the database server is installed, use the following command to restart MySql server

 ```
 sudo service mysql restart 
```

Next step is to install PHP 7.3. First make sure your Ubuntu server have the latest packages by running the following command

 ```
 sudo apt update <br></br> sudo apt upgrade
```

Next, add the ondrej/php which has PHP 7.3 package and other required PHP extensions.

 ```
 sudo apt install software-properties-common 
 sudo add-apt-repository ppa:ondrej/php
 sudo apt update

```

After adding the PPA you can now install PHP 7.3 for Nginx by using the following command.

 ```
 sudo apt install php7.3-fpm
```

You can confirm that PHP 7.3 FPM has been successfully installed by using the following command.

 ```
 php -v
```

After, PHP installation please run the following command to install the required PHP Modules for Joomla

 ```
 sudo apt install libapache2-mod-php7.3 php7.3-common php7.3-mbstring php7.3-xmlrpc php7.3-soap php7.3-gd php7.3-xml php7.3-intl php7.3-mysql php7.3-cli php7.3-mcrypt php7.3-ldap php7.3-zip php7.3-curl 
```

Now, you have installed all the required software and the next step is to login to mysql server and create Joomla database. Use following command to create database. Change with your database name.

 ```
 CREATE DATABASE  
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Next, run the commands below to download and extract the downloaded file and move it into a new Joomla root directory.

 ```
 cd /tmp && wget https://downloads.joomla.org/cms/joomla3/3-9-19/Joomla_3-9-19-Stable-Full_Package.zip?format=zip 
 sudo apt-get install unzip
 sudo unzip Joomla*.zip
 sudo mkdir -p /var/www/html/joomla
 sudo unzip Joomla*.zip -d /var/www/html/joomla
 sudo chown -R www-data:www-data /var/www/html/joomla/
 sudo chmod -R 755 /var/www/html/joomla/

```

Now, Lets configure joomla. Open your browser navigate to your domain name to start configuration of Joomla. You should see Joomla installation wizard

- Fill the form according to your configuration than press next
- Enter your database configuration and press next
- Now Install
 
Congrats. You have successfully installed Joomla on NGINX
