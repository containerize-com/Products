---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Install ILIAS on Ubuntu 18.04 LTS with Nginx

#### Install Nginx Web Server

Nginx is the most popular and secure web server. In order to install Nginx, use the following command

 ```
 sudo apt install nginx 
```

Once the Nginx is install, configure the domain and restart the Nginx by using the following command

 ```
 sudo service nginx restart 
```

#### Install MySQL Server

Next, need to install database Server, use the following command to install MySql server

 ```
sudo apt-get update;  
sudo apt-get install mysql-server; 
mysql_secure_installation 
```

Once, the database server is installed, use the following command to restart MySql server

 ```
sudo service mysql restart 
```

### Install PHP 7.2 and Related Modules

Run commands to add a third-party PPA to Ubuntu.

 ```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```

Now, run the following command to install PHP 7.2 and related modules.

 ```
sudo apt install php7.2-fpm php7.2-common php7.2-sqlite3 php7.2-mysql php7.2-gmp php7.2-curl php7.2-intl php7.2-mbstring php7.2-xmlrpc php7.2-gd php7.2-bcmath php7.2-xml php7.2-cli php7.2-zip
```

#### Create Database for ILIAS

Now, you have installed all the required software and the next step is to login to mysql server and create ILIAS database. Use following command to create database. Change with your database name.

 ```
CREATE DATABASE ilias; 
```

Create a database user called "ilias" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'iliasuser'@'localhost' IDENTIFIED BY 'password_here'; 
GRANT ALL ON ilias.* TO 'iliasuser'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES; EXIT;
```

#### Download ILIAS

Next, run the commands below to change directory and download ILIAS.

 ```
cd /var/www/html
sudo git clone https://github.com/ILIAS-eLearning/ILIAS.git ilias

```

Command to create directory outside the root directory of ilias and set permissions.

 ```
sudo mkdir /var/www/html/extras
sudo chown -R www-data:www-data /var/www/html/extras/
```

Run the following commands to set permissions.

 ```
sudo chown -R www-data:www-data /var/www/html/ilias/
sudo chmod -R 755 /var/www/html/ilias/
```

Create Nginx config file for ILIAS site.

 ```
sudo nano /etc/nginx/sites-available/ilias

```

Add below code into it and save the file.

 ```
server {
    listen 80;
    listen [::]:80;
    root /var/www/html/ilias;
    index  index.php index.html index.htm;
    server_name  example.com;

    client_max_body_size 100M;
    autoindex off;
    location / {
        try_files $uri $uri/ =404;
    }

    location ~ [^/].php(/|$) {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.2-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}

```

Create symlink to enable newly created site.

 ```
sudo ln -s /etc/nginx/sites-available/ilias /etc/nginx/sites-enabled/

```

Restart Nginx web server.

 ```
sudo systemctl restart nginx

```

Now, open browser and type http://example.com to access the site. Follow installation wizard to install ILIAS.
