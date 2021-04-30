---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Mailtrain on Ubuntu 16.04 LTS using Github

### Install Node.js and NPM

Install Node.js by using NodeSource APT repository.

 ```
 
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt install -y nodejs 

```

Check the Node.js and npm versions.

 ```
 
node -v && npm -v
# v8.11.1
# 5.6.0 

```

### Install MySQL Server

Next, need to install database Server, use the following command to install MySql server

 ```
 sudo apt-get update;  sudo apt-get install mysql-server; mysql_secure_installation 
```

Once, the database server is installed, use the following command to restart MySql server

 ```
sudo systemctl restart mysql 
```

Create mailtrain database. Use following command to create database.

 ```
CREATE DATABASE mailtrain 
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

### Install Nginx web server

Run below command to install Nginx.

 ```
sudo apt install nginx
```

Configure Nginx as reverse proxy. Run below command and add sample code in configuration file.

 ```
sudo nano /etc/nginx/sites-available/mailtrain.conf
```

 ```
 
server {

    listen [::]:80;
    listen 80;

    server_name example.com;

    charset utf-8;
    client_max_body_size 50M;


    location / {
        proxy_set_header Host $http_host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_pass http://127.0.0.1:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_next_upstream error timeout http_502 http_503 http_504;
    }

}

```

Create symlink for mailtrain.conf configuration file so Nginx can use it for loading of application.

 ```
sudo ln -s /etc/nginx/sites-available/mailtrain.conf /etc/nginx/sites-enabled/
```

Restart Nginx web server.

 ```
sudo systemctl restart nginx
```

### Install and Configure Mailtrain

Create directory for Mailtrain installation.

 ```
sudo mkdir -p /var/www/html/mailtrain
```

Navigate to the document root directory of Mailtrain.

 ```
cd /var/www/html/mailtrain
```

Download and unzip Mailtrain.

 ```

wget https://github.com/Mailtrain-org/mailtrain/archive/master.zip
unzip master.zip
Run npm install

```

Copy config/default.toml as config/production.toml and update database settings.

 ```

sudo cp config/default.toml config/production.toml
sudo nano config/production.toml

```

Run the server.

 ```
NODE_ENV=production npm start
```

Congrats! You have successfully installed Mailtrain.
