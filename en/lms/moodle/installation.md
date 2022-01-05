---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Moodle on Ubuntu 18.04 LTS with Nginx**

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

### Install PHP 7.4 and Related Modules

Run commands to add a third-party PPA to Ubuntu.

 ```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```

Now, run the following command to install PHP 7.4 and related modules.

 ```
sudo apt install php7.4-fpm php7.4-common php7.4-mysql php7.4-gmp php7.4-curl php7.4-intl php7.4-mbstring php7.4-soap php7.4-xmlrpc php7.4-gd php7.4-xml php7.4-cli php7.4-zip
```

#### Create Database for Moodle

Now, you have installed all the required software and the next step is to login to mysql server and create Moodle database. Use following command to create database. Change with your database name.

 ```
CREATE DATABASE moodle; 
```

Create a database user called "moodle" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'moodleuser'@'localhost' IDENTIFIED BY 'password_here'; 
GRANT ALL ON moodle.* TO 'moodleuser'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES; EXIT;
```

#### Download Moodle

Next, run the commands below to change directlory download and download Moodle.

 ```
cd /var/www/
sudo git clone -b MOODLE_38_STABLE git://git.moodle.org/moodle.git moodle

```

Run the following commands to set permissions.

 ```
sudo mkdir -p /var/www/moodledata
sudo chown -R www-data:www-data /var/www/
sudo chmod -R 755 /var/www/
sudo chown www-data:www-data /var/www/moodledata

```

Create Nginx config file for Moodle site.

 ```
sudo nano /etc/nginx/sites-available/moodle

```

Add below code into it and save the file.

 ```
server {
    listen 80;
    listen [::]:80;
    root /var/www/moodle;
    index  index.php index.html index.htm;
    server_name  example.com;

    client_max_body_size 100M;
    autoindex off;
    location / {
        try_files $uri $uri/ =404;
    }

    location /dataroot/ {
      internal;
      alias /var/www/moodledata/;
    }

    location ~ [^/].php(/|$) {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/run/php/php7.4-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}

```

Create symlink to enable newly created site.

 ```
sudo ln -s /etc/nginx/sites-available/moodle /etc/nginx/sites-enabled/

```

Restart Nginx web server.

 ```
sudo systemctl restart nginx

```

Now, open browser and type http://example.com to access the site. Follow installation wizard to install Moodle.
