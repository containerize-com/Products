---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Install OpenCart on Ubuntu

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

Now, you have installed all the required software and the next step is to login to mysql server and create zencart database. Use following command to create database. Change with your database name.

 ```
 CREATE DATABASE  
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Run the commands below to download and extract the downloaded file and move it into a zencart root directory.

 ```

cd /tmp && wget https://downloads.sourceforge.net/project/zencart/CURRENT%20-%20Zen%20Cart%201.5.x%20Series/zen-cart-v1.5.5e-03082017.zip
unzip zen-cart-v1.5.5e-03082017.zip
sudo mv zen-cart-v1.5.5e-03082017 /var/www/html/zencart

```

Set correct permissions for Zen Cart.

 ```

sudo chown -R www-data:www-data /var/www/html/zencart/
sudo chmod -R 755 /var/www/html/zencart/

```

Create Nginx configuration file for Zen Cart.

 ```
sudo nano /etc/nginx/sites-available/zencart
```

Copy and paste the content below into the file and save it. Replace example.com with your own domain.

 ```

server {
    listen 80;
    listen [::]:80;
    root /var/www/html/zencart;
    index  index.php index.html index.htm;
    server_name  example.com;

    location / {
    try_files $uri $uri/ /index.php?main_page=$uri&$args;       
    }

    location ~ [^/]\.php(/|$) {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.1-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

}

```

Create symlink for zencart file.

 ```
sudo ln -s /etc/nginx/sites-available/zencart /etc/nginx/sites-enabled/
```

Restart Nginx.

 ```
sudo systemctl restart nginx
```

Open your site in browser and follow installation wizard.