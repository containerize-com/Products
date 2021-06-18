---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Install Chamilo on Ubuntu 18.04 LTS with Nginx

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
sudo apt install php7.2-fpm php7.2-common php7.2-sqlite3 php7.2-curl php7.2-intl php7.2-mbstring php7.2-xmlrpc php7.2-mysql php7.2-gd php7.2-xml php7.2-cli php7.2-ldap php7.2-apcu php7.2-zip
```

#### Create Database for Chamilo

Now, you have installed all the required software and the next step is to login to mysql server and create Chamilo database. Use following command to create database. Change with your database name.

 ```
CREATE DATABASE chamilo; 
```

Create a database user called "chamilo" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'chamilouser'@'localhost' IDENTIFIED BY 'password_here'; 
GRANT ALL ON chamilo.* TO 'chamilouser'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES; EXIT;
```

#### Download Chamilo

Next, run the commands below to download Chamilo, unzip and move it to Nginx web server directory.

 ```
cd /tmp && wget https://github.com/chamilo/chamilo-lms/releases/download/v1.11.6/chamilo-1.11.6-php7.zip
unzip chamilo-1.11.6-php7.zip
sudo mv chamilo-1.11.6 /var/www/html/chamilo

```

Run the following commands to set permissions.

 ```
sudo chown -R www-data:www-data /var/www/html/chamilo/
sudo chmod -R 755 /var/www/html/chamilo/

```

Create Nginx config file for Chamilo site.

 ```
sudo nano /etc/nginx/sites-available/chamilo

```

Add below code into it and save the file.

 ```
server {
    listen 80;
    listen [::]:80;
    root /var/www/html/chamilo;
    index  index.php index.html index.htm;
    server_name  example.com;

    client_max_body_size 100M;

    location / {
        try_files $uri /index.php$is_args$args;
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
sudo ln -s /etc/nginx/sites-available/chamilo /etc/nginx/sites-enabled/

```

Restart Nginx web server.

 ```
sudo systemctl restart nginx

```

Now, open browser and type http://example.com to access the site. Follow the installation wizard to install Chamilo.
