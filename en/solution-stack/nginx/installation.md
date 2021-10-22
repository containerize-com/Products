---
title: Installation Instructions
onpagelink: installation
weight: 3

---


### **Installation**

Install NGINX from Ubuntu’s default repositories using apt command

    sudo apt update
    sudo apt install nginx

Next you need to adjust the firewall

    sudo ufw app list

Then it will show available applications

*   NGINX Full
*   NGINX HTTP
*   OpenSSH
*   NGINX HTTPS

It is recommended to enable the most restrictive profile. Since the SSL is not configured, allow non SSL traffic for now

    sudo ufw allow 'Nginx HTTP'

Now verify the status

    sudo ufw status

Next we need to verify installation status

    systemctl status nginx

Use server’s IP address to to access the default NGINX landing page. Here are some methods to get server’s IP address

    ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'

Another way to get server’s public IP address is

    curl -4 icanhazip.com

When you have your server’s IP address, enter it into your browser’s address bar:

    http://your_server_ip

That’s it. NGINX is installed successfully.

#### Some Helpful Commands

Stop web server

    sudo systemctl stop nginx

Start web server

    sudo systemctl start nginx

Stop and then start the server

    sudo systemctl restart nginx

Reload web server

    sudo systemctl reload nginx

Disable and Enable NGINX

    sudo systemctl disable nginx

To re-enable the service to start up at boot, you can type:

    sudo systemctl enable nginx
