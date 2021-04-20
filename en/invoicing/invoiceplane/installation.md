---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install InvoicePlane on Ubuntu 16.04/18.04 LTS with Nginx using GitHub

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

Now, you have installed all the required software and the next step is to login to mysql server and create invoiceplane database. Use following command to create database.

 ```
 CREATE DATABASE  invoiceplane;
```

Create a database user called "invoiceplane" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'invoiceplane'@'localhost' IDENTIFIED BY 'new_password_here'; 
GRANT ALL ON invoiceplane.* TO 'invoiceplane'@'localhost' IDENTIFIED BY 'user_password_here' WITH GRANT OPTION;
FLUSH PRIVILEGES; 
EXIT;
```

### Download InvoicePlane Latest Release

Install Git, Curl and Composer to get started.

 ```
 
sudo apt install curl git
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
sudo composer install

```

Change into the Nginx root directory and download InvoicePlane from GitHub.

 ```

cd /var/www/html
sudo git clone https://github.com/InvoicePlane/InvoicePlane.git
cd /var/www/html/InvoicePlane

```

Copy ipconfig file with below command.

 ```

sudo cp /var/www/html/InvoicePlane/ipconfig.php.example /var/www/html/InvoicePlane/ipconfig.php

```

Edit ipconfig file and change site URL.

 ```

sudo nano ipconfig.php

```

Set correct permissions for InvoicePlane to function.

 ```

sudo chown -R www-data:www-data /var/www/html/InvoicePlane/
sudo chmod -R 755 /var/www/html/InvoicePlane/

```

Congrats! You have successfully installed InvoicePlane on Ubuntu

#### **Explore**

You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
 