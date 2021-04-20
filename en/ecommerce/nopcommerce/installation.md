---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing on Windows

First, you need to download it from https://www.nopcommerce.com/download-nopcommerce

After downloading, uplodad files on your web server using FTP software.

Create database for your nopCommerce project.

Open browser and visit your site, it will redirect to the installation wizard. Fill Store and Database information details.

Click Install button in order to start the installation process. Project home page will display once installation is complete.

### Installing on Linux

Run below command to register Microsoft key and feed.

 ```
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb

```

Install the .NET core runtime.

 ```
sudo apt-get install apt-transport-https aspnetcore-runtime-3.1
```

Install the Nginx web server.

 ```
sudo apt-get install nginx
```

Install the MySql server.

 ```
sudo apt-get install mysql-server
```

Secure MySQL installation.

 ```
sudo mysql_secure_installation
```

Configure nginx as a reverse proxy to forward requests to your ASP.NET Core application. Open Nginx default config file with below command.

 ```
sudo nano /etc/nginx/sites-available/default
```

Replace the contents with the following and save it.

 ```

# Default server configuration
#
server {
    listen 80 default_server;
    listen [::]:80 default_server;

    server_name   nopCommerce-430.com;

    location / {
    proxy_pass         http://localhost:5000;
    proxy_http_version 1.1;
    proxy_set_header   Upgrade $http_upgrade;
    proxy_set_header   Connection keep-alive;
    proxy_set_header   Host $host;
    proxy_cache_bypass $http_upgrade;
    proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header   X-Forwarded-Proto $scheme;
    }

```

Create a directory for project.

 ```
sudo mkdir /var/www/nopCommerce430
```

Go to project root directory.

 ```
cd /var/www/nopCommerce430
```

Download the nopCommerce.

 ```
sudo wget https://github.com/nopSolutions/nopCommerce/releases/download/release-4.30/nopCommerce_4.30_NoSource_linux_x64.zip
```

Run command to unzip project.

 ```
sudo unzip nopCommerce_4.30_NoSource_linux_x64.zip
```

Create following directories to run nopCommerce.

 ```
sudo mkdir bin
sudo mkdir logs

```

Set correct permissions to run nopCommerce.

 ```
sudo chgrp -R www-data /var/www/nopCommerce430/
sudo chown -R www-data /var/www/nopCommerce430/

```

Create the nopCommerce service. Run below command to create service file.

 ```
sudo nano /etc/systemd/system/nopCommerce430.service
```

Copy below content and past in service file.

 ```

[Unit]
Description=Example nopCommerce app running on XUbuntu

[Service]
WorkingDirectory=/var/www/nopCommerce430
ExecStart=/usr/bin/dotnet /var/www/nopCommerce430/Nop.Web.dll
Restart=always
# Restart service after 10 seconds if the dotnet service crashes:
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=nopCommerce430-example
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false

[Install]
WantedBy=multi-user.target

```

Start the nopCommerce service.

 ```
sudo systemctl start nopCommerce430.service
```

Restart Nginx web server to load new configurations.

 ```
sudo systemctl restart nginx
```

Open browser and visit your site, it will redirect to the installation wizard. Fill Store and Database information details.

Click Install button in order to start the installation process. Project home page will display once installation is complete.

#### **Explore**

You may find the following links relevant:

- [Top 5 Open Source Shopping Cart Software in 2020](https://blog.containerize.com/2020/11/27/top-5-open-source-shopping-cart-software-in-2020/)
 