---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Flarum on Ubuntu 18.04 LTS with Composer

You will need to install Apache, MariaDB and PHP to your system. First, install Apache and MariaDB using the following command:

    sudo apt-get install apache2 mariadb-server -y

Next, install PHP 7.1 to your system. But, PHP 7.1 is not available in Ubuntu 18.04 default repository. So you will need to add the repository for PHP first. You can add it with the following command:

    sudo apt-get install python-software-properties -ysudo add-apt-repository -y ppa:ondrej/php

After installing PHP repository, install PHP7.1 along with all the required libraries using the following command:

    sudo apt-get install php7.1 libapache2-mod-php7.1 php7.1-common php7.1-mbstring php7.1-xmlrpc php7.1-soap php7.1-mysql php7.1-gd php7.1-xml php7.1-cli php7.1-zip wget unzip curl git -y

Next, you will also need to make some changes in php.ini file:

    sudo nano /etc/php/7.1/apache2/php.ini

Make the following changes:

    file_uploads = On
    allow_url_fopen = On
    memory_limit = 256M
    upload_max_file_size = 150M
    max_execution_time = 450

Save and close the file, when you are finished. Then, start Apache and MariaDB service and enable them to start on boot with the following command:

    sudo systemctl start apache2sudo systemctl start mysqlsudo systemctl enable apache2sudo systemctl enable mysql

By default, the MariaDB is not secured. So you will need to secure it first. You can secure it by running the mysql\_secure\_installation script:

    mysql_secure_installation

Answer all the questions as shown below:

    Enter current password for root (enter for none): Enter
    Set root password? [Y/n]: Y
    New password: 
    Re-enter new password: 
    Remove anonymous users? [Y/n]: Y
    Disallow root login remotely? [Y/n]: Y
    Remove test database and access to it? [Y/n]: Y
    Reload privilege tables now? [Y/n]: Y

Next, log into MariaDB shell with the following command:

    mysql -u root -p

Enter your root password, then create a Flarum database:

    CREATE DATABASE flarumdb;

Next, create a Flarum user with the following command:

    GRANT ALL PRIVILEGES ON flarumdb.* TO 'flarum'@'localhost' IDENTIFIED BY 'password';FLUSH PRIVILEGES;EXIT

Next, you will need to install Composer to your system. You can install Composer with the following command:

    sudo curl -s https://getcomposer.org/installer | phpsudo mv composer.phar /usr/local/bin/composer

Next, create a directory under Apache web root for Flarum project and install via Composer:

    sudo mkdir /var/www/html/flarumcd /var/www/html/flarumsudo composer create-project flarum/flarum . --stability=betasudo chown -R www-data:www-data /var/www/html/flarum/sudo chmod -R 755 /var/www/html/flarum/

Next, create an apache virtual host directive for Flarum:

    sudo nano /etc/apache2/sites-available/flarum.conf

Add the following lines:

    <VirtualHost *:80>
     ServerAdmin admin@yourdomain.com
     DocumentRoot /var/www/html/flarum
     ServerName yourdomain.com
     <Directory /var/www/html/flarum/>
    Options +FollowSymLinks
    AllowOverride All
    Order allow,deny
    allow from all
     </Directory>
     ErrorLog /var/log/apache2/flarum-error_log
     CustomLog /var/log/apache2/flarum-access_log common
    </VirtualHost>

Save and close the file, then enable virtual host file and rewrite module with the following command:

    sudo a2ensite flarum sudo a2enmod rewrite

Finally, restart Apache web server to apply all the changes. Open your web browser and nevigate to URL http://yourdomain.com to access Flarum.

### Installation using Docker

Pull Flarum Image from hub.docker.com:

    docker pull mondedie/flarum:latest

Configure Docker-compose.yml:

    version: “3”
    
    services:
    flarum:
    image: mondedie/flarum:stable
    container_name: flarum
    env_file:
    – /mnt/docker/flarum/flarum.env
    volumes:
    – /mnt/docker/flarum/assets:/flarum/app/public/assets
    – /mnt/docker/flarum/extensions:/flarum/app/extensions
    – /mnt/docker/flarum/nginx:/etc/nginx/conf.d
    depends_on:
    – mariadb
    
    mariadb:
    image: mariadb:10.4
    container_name: mariadb
    environment:
    – MYSQL_ROOT_PASSWORD=xxxxxxxxxx
    – MYSQL_DATABASE=flarum
    – MYSQL_USER=flarum
    – MYSQL_PASSWORD=xxxxxxxxxx
    volumes:
    – /mnt/docker/mysql/db:/var/lib/mysql
    

Create an environment file:

    # vi /mnt/docker/flarum/flarum.env
    
    DEBUG=false
    FORUM_URL=http://domain.tld
    
    # Database configuration
    DB_HOST=mariadb
    DB_NAME=flarum
    DB_USER=flarum
    DB_PASS=xxxxxxxxxx
    DB_PREF=flarum_
    DB_PORT=3306
    
    # User admin flarum (environment variable for first installation)
    # /!\ admin password must contain at least 8 characters /!\
    FLARUM_ADMIN_USER=admin
    FLARUM_ADMIN_PASS=xxxxxxxxxx
    FLARUM_ADMIN_MAIL=admin@domain.tld
    FLARUM_TITLE=Test flarum
    

Run your docker-compose:

    docker-compose up -d mariadb
    docker-compose up -d flarum
    

Congrats! You have successfully installed Flarum