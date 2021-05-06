---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install InvoiceNinja on Ubuntu 16.04 LTS with Nginx using Github

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

Now, you have installed all the required software and the next step is to login to mysql server and create invoiceninja database. Use following command to create database.

 ```
 CREATE DATABASE  invoiceninja;
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
CREATE USER 'invoiceninjauser'@'localhost' IDENTIFIED BY 'new_password_here'; 
GRANT ALL ON invoiceninja.* TO 'invoiceninjauser'@'localhost' IDENTIFIED BY 'user_password_here' WITH GRANT OPTION;
FLUSH PRIVILEGES; 
EXIT;
```

Download InvoiceNinja Latest Release

 ```
 
sudo apt install curl git
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

```

After installing curl and Composer above, change into the Nginx root directory and downaload Invoice Ninja packages from Github.

 ```

cd /var/www/html
sudo git clone https://github.com/invoiceninja/invoiceninja.git
cd /var/www/html/invoiceninja
sudo composer install

```

Then run the commands below to set the correct permissions for InvoiceNinja to function.

 ```

sudo chown -R www-data:www-data /var/www/html/invoiceninja/
sudo chmod -R 755 /var/www/html/invoiceninja/

```

Congrats! You have successfully installed InvoiceNinja on NGINX

### Installation using Docker

Generate an application key

 ```

docker run --rm -it invoiceninja/invoiceninja php artisan key:generate --show

```

Create folders for data persistence

- Create two folder on your server, e. g. /var/invoiceninja/public and /var/invoiceninja/storage
- Mount these folders into your container
 
Usage: To run it

 ```

docker run -d \
  -v /var/invoiceninja/public:/var/app/public \
  -v /var/invoiceninja/storage:/var/app/storage \
  -e APP_ENV='production' \
  -e APP_DEBUG=0 \
  -e APP_URL='http://ninja.dev' \
  -e APP_KEY='' \
  -e APP_CIPHER='AES-256-CBC' \
  -e DB_TYPE='mysql' \
  -e DB_STRICT='false' \
  -e DB_HOST='localhost' \
  -e DB_DATABASE='ninja' \
  -e DB_USERNAME='ninja' \
  -e DB_PASSWORD='ninja' \
  -p '9000:9000' \
  invoiceninja/invoiceninja

```
