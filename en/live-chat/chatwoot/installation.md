---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation guide for Linux VM**

#### Deploying to Linux VM

This guide will help you to install Chatwoot on Ubuntu 18.04 LTS / 20.04 LTS / 20.10. We have prepared a deployment script for you to run. Refer the script and feel free to make changes accordingly to OS if you are on a non-Ubuntu system.

For Ubuntu 18.04, use the following script

    https://raw.githubusercontent.com/chatwoot/chatwoot/develop/deployment/setup_18.04.sh 

For Ubuntu 20.04 or Ubuntu 20.10, use the following script.

    https://raw.githubusercontent.com/chatwoot/chatwoot/develop/deployment/setup_20.04.sh
      

#### Steps to install

Create a setup.sh file and copy the content from the above link or use the following commands

     wget  -O setup.sh
    chmod 755 setup.sh
    ./setup.sh master 

Execute the script and it will take care of the initial Chatwoot setup.

Chatwoot Installation will now be accessible at http://{your\_ip\_address}:3000

#### Configure Nginx and Let's Encrypt

Configure Nginx to serve as a frontend proxy.

    cd /etc/nginx/sites-enabled
    nano yourdomain.com.conf  

Use the following Nginx config after replacing the yourdomain.com in server\_name .

    server {
      server_name ;
    
      # Point upstream to Chatwoot App Server
      set $upstream 127.0.0.1:3000;
    
      # Nginx strips out underscore in headers by default
      # Chatwoot relies on underscore in headers for API
      # Make sure that the config is turned on.
      underscores_in_headers on;
      location /.well-known {
        alias /var/www/ssl-proof/chatwoot/.well-known;
      }
    
      location / {
        proxy_pass_header Authorization;
        proxy_pass http://$upstream;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header X-Forwarded-Ssl on; # Optional
    
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    
        proxy_http_version 1.1;
        proxy_set_header Connection “”;
        proxy_buffering off;
    
        client_max_body_size 0;
        proxy_read_timeout 36000s;
        proxy_redirect off;
      }
      listen 80;
    }  

Verify and reload your Nginx config by running following command.

     nginx -t
    systemctl reload nginx 

Run Let's Encrypt and configure SSL certificate.

     mkdir -p /var/www/ssl-proof/chatwoot/.well-known
    certbot --webroot -w /var/www/ssl-proof/chatwoot/ -d yourdomain.com -i nginx 

Your Chatwoot installation should be accessible from the https://yourdomain.com now.

#### Configure the required environment variables

For your Chatwoot installation to properly function you would need to configure some of the essential environment variables like FRONTEND\_URL, Mailer and a cloud storage config. Refer Environment variables for the full list.

Login as Chatwoot and edit the .env file.

    # Login as chatwoot user
    
    sudo -i -u chatwoot
    cd chatwoot
    nano .env  

Update the required environment variables and restart the Chatwoot server and enjoy using your self hosted Chatwoot

     systemctl restart chatwoot.target
