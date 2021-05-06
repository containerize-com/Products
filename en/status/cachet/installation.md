---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Cachet on Ubuntu 16.04 LTS with Nginx using Github

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

To get Cachet latest release you may want to use Github repository… Install git tool to download Cachet packages.

 ```
 
sudo apt install curl git
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

```

After installing curl above, change into the Apache2 root directory and download Cachet packages from Github.

 ```
 
cd /var/www/html
sudo git clone -b 2.4 --single-branch https://github.com/cachethq/Cachet.git cachet

```

Next the commands below to create Cachet .env file. Then update the database connection setting and save the file.

 ```
 
sudo cp /var/www/html/cachet/.env.example /var/www/html/cachet/.env
sudo nano /var/www/html/cachet/.env

```

After that, run the commands below to use composer to install all required package.

 ```
 
cd /var/www/html/cachet
sudo composer install --no-dev -o

```

Set up the application key by running and install Cachet.

 ```
 
sudo php artisan key:generate
sudo php artisan cachet:install

```

Then run the commands below to set the correct permissions for Cachet root directory.

 ```
 
sudo chown -R www-data:www-data /var/www/html/cachet/
sudo chmod -R 755 /var/www/html/cachet/

```

Congrats! You have successfully installed Cachet on NGINX

### Installation using Docker

Getting started with Docker Compose. Quickly launch Cachet, NGINX and PostgreSQL docker images with docker-compose.

Clone the repository

 ```
 
$ git clone https://github.com/cachethq/Docker.git cachet-docker
$ cd cachet-docker

```

Edit the docker-compose.yml file to specify your ENV variables.

To build an image containing a specific Cachet release, change the cachet\_ver ARG in the docker-compose.yml file.

 ```
 
cachet:
    build:
      context: .
      args:
        - cachet_ver=v2.3.10

```

Build and run the image

 ```
 
$ docker-compose build
$ docker-compose up

```

Continue to configure Cachet in your web browser by navigating to your Docker host's IP address.

Run a DB container.

 ```
 
$ docker run --name postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -d postgres:9.5

```

Run Cachet.

 ```
 
$ docker run -d --name cachet --link postgres -e DB_DRIVER=pgsql -e DB_HOST=postgres -e DB_DATABASE=postgres -e DB_USERNAME=postgres -e DB_PASSWORD=postgres -d cachethq/docker:latest

```

Now go to "http://ipdockerisboundto:8000/setup" and follow steps for configurations.
