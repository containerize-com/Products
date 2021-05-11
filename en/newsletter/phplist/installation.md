---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Install phpList on Ubuntu 16.04 LTS with Nginx

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

Now, you have installed all the required software and the next step is to login to mysql server and create phplist database. Use following command to create database. Change with your database name.

 ```
 CREATE DATABASE  
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Next, run the commands below to download and extract the downloaded file and move it into a new phplist root directory.

 ```
 
 wget http://prdownloads.sourceforge.net/phplist/phplist-3.5.5.zip 
 unzip phplist-3.5.5.zip
 mv phplist-3.5.5/public_html/lists/ /var/www/html/phplist

```

Edit phplist config.php file. Adjust database and SMTP settings to reflect with your own values.

 ```
 
nano /var/www/html/phplist/config/config.php

```

Now, Lets configure phpList. Open your browser navigate to your domain name to start configuration of phpList. You should see phpList installation wizard

- Click on the Initialise Database button.
- Enter the your name, organization name, email address, and administrative login user name. The initial login name will be “admin”.
- Once, the initialization is completed, click on the phpList Setup button to start phpList further configuration.
 
Congrats! You have successfully installed phpList on NGINX
