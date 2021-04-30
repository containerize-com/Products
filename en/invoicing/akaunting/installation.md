---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Akaunting on Ubuntu 18.04 LTS with Nginx using downloaded package

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

Install PHP for processing

 ```
 sudo apt-get install php-fpm php-mysql
```

Now, you have installed all the required software and the next step is to login to mysql server and create akaunting database. Use following command to create database.

 ```
 CREATE DATABASE  akaunting;
```

Create a database user called "akaunting" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'akaunting'@'localhost' IDENTIFIED BY 'new_password_here'; 
GRANT ALL ON akaunting.* TO 'akaunting'@'localhost' IDENTIFIED BY 'user_password_here' WITH GRANT OPTION;
FLUSH PRIVILEGES; 
EXIT;
```

Download the latest Akaunting package and unzip it with below commands.

 ```
 
cd /tmp && curl -O -J -L https://akaunting.com/download.php?version=latest
sudo mkdir -p /var/www/html/akaunting
sudo unzip Akaunting_1.2.12-Stable.zip -d /var/www/html/akaunting/

```

Set the correct permissions for web server user.

 ```

sudo chown -R www-data:www-data /var/www/html/akaunting/
sudo chmod -R 755 /var/www/html/akaunting/

```

Congrats! You have successfully installed Akaunting on NGINX

