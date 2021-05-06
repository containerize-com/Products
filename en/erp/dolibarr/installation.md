---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installing ERPNext on Ubuntu 18.04

Update and Upgrade APT.

 ```

sudo apt-get update 
sudo apt-get upgrade

```

Install Nginx.

 ```
sudo apt-get install nginx
```

Run below command to install MariaDB.

 ```
sudo apt-get install mariadb-server mariadb-client
```

Run the commands below to secure MariaDB server. Answer the questions when prompted.

 ```
sudo mysql_secure_installation
```

Connect to MariaDB server.

 ```
sudo mysql -u root -p
```

Create a database with named dolibarr.

 ```
CREATE DATABASE dolibarr;
```

Create a database user called dolibarruser. Replace password\_here with your own password.

 ```
CREATE USER 'dolibarruser'@'localhost' IDENTIFIED BY 'password_here';
```

Grant the user full access to the database.

 ```

GRANT ALL ON dolibarr.* TO 'dolibarruser'@'localhost' IDENTIFIED BY 'password_here' WITH GRANT OPTION;

```

Save changes and exit.

 ```

FLUSH PRIVILEGES;
exit;

```

Run the below commands to add third party repository for PHP-FPM installation.

 ```

sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php

```

Run below command to update package repositories.

 ```
sudo apt update
```

Execute command to install PHP 7.1.

 ```

sudo apt install php7.1-fpm php7.1-common php7.1-curl php7.1-intl php7.1-mbstring php7.1-mcrypt php7.1-json php7.1-xmlrpc php7.1-soap php7.1-mysql php7.1-gd php7.1-xml php7.1-cli php7.1-zip

```

Restart Nginx.

 ```
sudo systemctl restart nginx
```

Run the below command to get latest Dolibarr release.

 ```
cd /tmp && wget https://sourceforge.net/projects/dolibarr/files/Dolibarr%20ERP-CRM/7.0.2/dolibarr-7.0.2.zip

```

Unzip and move project to web server root direrectory.

 ```

sudo unzip dolibarr-7.0.2.zip
sudo mv dolibarr-7.0.2 /var/www/html/dolibarr

```

Set the correct permissions for Dolibarr.

 ```

sudo chown -R www-data:www-data /var/www/html/dolibarr/
sudo chmod -R 755 /var/www/html/dolibarr/

```

Create Nginx configuration file for Dolibarr.

 ```
sudo nano /etc/nginx/sites-available/dolibarr
```

Copy and paste the content below into the file and save it. Replace example.com with your own domain.

 ```

server {
    listen 80;
    listen [::]:80;
    root /var/www/html/dolibarr;
    index  index.php index.html index.htm;
    server_name  example.com;

    location / {
    try_files $uri $uri/ =404;        
    }

    location ~ [^/]\.php(/|$) {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.1-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

}

```

Create symlink for dolibarr file.

 ```
sudo ln -s /etc/nginx/sites-available/opencart /etc/nginx/sites-enabled/
```

Restart Nginx.

 ```
sudo systemctl restart nginx
```

Follow the wizard for Dolibarr installation.

