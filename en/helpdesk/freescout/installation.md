---
title: Installation Guide
onpagelink: installation
weight: 3

---
### **Installation**

#### Installation using Github

Let’s first install nigix with following commands:

    sudo apt-get update
    sudo apt install nginx


Next, install PHP and required modules:

    sudo apt install php7.0 php7.0-mysqli php7.0-fpm php7.0-mbstring php7.0-xml php7.0-imap php7.0-json php7.0-zip php7.0-gd

Next, install MySQL with following command:

    sudo apt install mysql-server libmysqlclient-dev

Now, run following command to install git:

    sudo apt install git

Login to MySQL and create FreeScout database and user:

    CREATE DATABASE `freescout` CHARSET utf8mb4 COLLATE utf8mb4_unicode_ci;
    GRANT ALL PRIVILEGES ON `freescout`.* TO `freescout`@`localhost` IDENTIFIED BY “XXX”;
    EXIT;


Create FreeScout directory and download application from github.

    mkdir -p /var/www/html
    sudo chown www-data:www-data /var/www/html
    cd /var/www/html
    git clone https://github.com/freescout-helpdesk/freescout


Change owner and assign permissions to user:

    chown -R www-data:www-data /var/www/html
    sudo usermod -a -G www-data freescout
    find /var/www/html -type f -exec chmod 664 {} \;
    find /var/www/html -type d -exec chmod 775 {} \;


Create nigix configuration file:

    sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/example.com
    rm /etc/nginx/sites-enabled/default
    ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/example.com
    sudo nano /etc/nginx/sites-enabled/example.com


Nigix config file should be like following:

    server {
    listen 80;
    listen [::]:80;
    
    server_name example.com http://www.example.com;
    
    root /var/www/html/public;
    
    index index.php index.html index.htm;
    
    error_log /var/www/html/storage/logs/web-server.log;
    
    location / {
    try_files $uri $uri/ /index.php?$query_string;
    }
    location ~ \.php$ {
    fastcgi_split_path_info ^(.+\.php)(/.+)$;
    fastcgi_pass unix:/run/php/php7.0-fpm.sock;
    fastcgi_index index.php;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    include fastcgi_params;
    }
    # Uncomment this location if you want to improve attachments downloading speed.
    # Also make sure to set APP_DOWNLOAD_ATTACHMENTS_VIA=nginx in the .env file.
    #location ^~ /storage/app/attachment/ {
    # internal;
    # alias /var/www/html/storage/app/attachment/;
    #}
    location ~* ^/storage/attachment/ {
    expires 1M;
    access_log off;
    try_files $uri $uri/ /index.php?$query_string;
    }
    location ~* ^/(?:css|js)/.*\.(?:css|js)$ {
    expires 2d;
    access_log off;
    add_header Cache-Control “public, must-revalidate”;
    }
    location ~* ^/(?:css|fonts|img|installer|js|modules|[^\\\]+\..*)$ {
    expires 1M;
    access_log off;
    add_header Cache-Control “public”;
    }
    location ~ /\. {
    deny all;
    }
    }


Next, Reload Nigix:

    nginx -t
    service nginx reload


Install Certbot and enable HTTPS:

    apt-get update
    apt-get install software-properties-common
    add-apt-repository universe
    add-apt-repository ppa:certbot/certbot
    apt-get update
    apt-get install certbot python-certbot-nginx
    certbot –nginx –register-unsafely-without-email
    certbot renew –dry-run


When asked choose option 2: Redirect – Make all requests redirect to secure HTTPS access. Setup cronjob for auto renewal.

    0 12 * * * /usr/bin/certbot renew –quiet

Finally, Open web installer https://example.com/install and follow instructions

#### Installation using Docker

Pull FreeScout Image from hub.docker.com:

    docker pull tiredofit/freescout

Configure Docker-compose.yml:

    version: ‘2’
    
    services:
    
    freescout-app:
    image: tiredofit/freescout
    container_name: freescout-app
    links:
    – freescout-db
    volumes:
    #### If you want to perform customizations to the source and have access to it, then uncomment this line – This includes modules
    #- ./data:/www/html
    #### Or, if you just want to use Stock Freescout and hold onto persistent files like cache and session use this, one or the other.
    – ./data:/data
    #### If you want to just keep the original source and add additional modules uncomment this line
    #- ./modules:/www/html/Modules
    – ./logs/:/www/logs
    environment:
    – VIRTUAL_HOST=freescout.example.com
    – VIRTUAL_NETWORK=nginx-proxy
    – VIRTUAL_PORT=80
    – LETSENCRYPT_HOST=freescout.example.com
    – LETSENCRYPT_EMAIL=admin@example.com
    
    – ZABBIX_HOSTNAME=freescout-app
    
    – DB_HOST=freescout-db
    – DB_NAME=freescout
    – DB_USER=freescout
    – DB_PASS=freescout
    
    – SITE_URL=https://freescout.example.com
    – ADMIN_EMAIL=admin@admin.com
    – ADMIN_PASS=freescout
    – ENABLE_SSL_PROXY=FALSE
    – DISPLAY_ERRORS=FALSE
    – TIMEZONE=America/Vancouver
    networks:
    – proxy-tier
    restart: always
    
    freescout-db:
    image: tiredofit/mariadb
    container_name: freescout-db
    volumes:
    – ./db:/var/lib/mysql
    environment:
    – ROOT_PASS=password
    – DB_NAME=freescout
    – DB_USER=freescout
    – DB_PASS=freescout
    
    – ZABBIX_HOSTNAME=freescout-db
    networks:
    – proxy-tier
    restart: always
    
    freescout-db-backup:
    container_name: freescout-db-backup
    image: tiredofit/db-backup
    links:
    – freescout-db
    volumes:
    – ./dbbackup:/backup
    environment:
    – ZABBIX_HOSTNAME=freescout-db-backup
    – DB_HOST=freescout-db
    – DB_TYPE=mariadb
    – DB_NAME=freescout
    – DB_USER=freescout
    – DB_PASS=freescout
    – DB_DUMP_FREQ=1440
    – DB_DUMP_BEGIN=0000
    – DB_CLEANUP_TIME=8640
    – COMPRESSION=BZ
    – MD5=TRUE
    networks:
    – proxy-tier
    restart: always
    networks:
    proxy-tier:
    external:
    name: nginx-proxy


Create an environment file. List of environment available at [https://github.com/tiredofit/docker-freescout#environment-variables](https://github.com/tiredofit/docker-freescout#environment-variables)

Map persistent storage, review data-volumes configuration at [https://github.com/tiredofit/docker-freescout#data-volumes](https://github.com/tiredofit/docker-freescout#data-volumes)

Make sure your desired ports are available and exposed. Finally run docker-compose.

Congrats! You have successfully installed FreeScout.
