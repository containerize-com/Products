---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Install Mautic on Ubuntu 17.04 LTS with Apache

Install Apache2 on Ubuntu by running the commands below:

 ```
sudo apt install apache2
 ```

Next, run the commands below to stop, start and enable Apache2 service to always start up with the server boots.

 ```
sudo systemctl stop apache2.service
sudo systemctl start apache2.service
sudo systemctl enable apache2.service
 ```

Next, need to install database Server, use the following command to install MariaDB server

 ```
 sudo apt-get update;  
sudo apt-get install mariadb-server mariadb-client; 
sudo systemctl stop mariadb.service
sudo systemctl start mariadb.service
sudo systemctl enable mariadb.service
mysql_secure_installation;

 ```

Once, the database server is installed, use the following command to restart MariaDB server

 ```
 sudo systemctl restart mariadb.service
 ```

Next step is to install PHP 7.3. First make sure your Ubuntu server have the latest packages by running the following command

 ```
 sudo apt update <br></br> sudo apt upgrade
 ```

Next, To install PHP and related modules run the commands below.

 ```
 sudo apt install php libapache2-mod-php libapache2-mod-php php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-tidy php-mysql php-cli php-mcrypt php-ldap php-zip php-curl php-sqlite3

 ```

 Make the change the following lines below in **php.ini** file and save.

 ```
file_uploads = On
allow_url_fopen = On
memory_limit = 256M
upload_max_filesize = 64M
max_execution_time = 360
date.timezone = America/Chicago
 ```

Now, you have installed all the required software and the next step is to login to database server and create Mautic database. Use following command to create database. Change with your database name.

 ```
CREATE DATABASE mauticdb;
 ```

Create a database user called mauticuser with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'mauticuser'@'localhost' IDENTIFIED BY 'new_password_here';
GRANT ALL ON mauticdb.* TO 'mauticuser'@'localhost' IDENTIFIED BY 'user_password_here' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;

 ```

Next, run the commands below to download and extract the downloaded file and move it into a new Mautic root directory.

 ```
cd /tmp && wget https://www.mautic.org/download/latest
sudo mkdir /var/www/html/mautic
sudo unzip latest -d /var/www/html/mautic
sudo chown -R www-data:www-data /var/www/html/mautic/
sudo chmod -R 755 /var/www/html/mautic/

 ```

Finally, configure Apahce2 site configuration file for Mautic and open your browser navigate to your domain name to start configuration of Mautic . You should see Mautic installation wizard

- Fill the form according to your configuration than press next
- Enter your database configuration and press next
- Now Install

Congrats! You have successfully installed Mautic on Apache
