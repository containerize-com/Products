---
title: Installation Instructions
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Install NGINX from Ubuntu’s default repositories using apt command

 ```
<pre class="wp-block-code">```
sudo apt update
sudo apt install nginx
```
```

Next you need to adjust the firewall

 ```
<pre class="wp-block-code">```
sudo ufw app list
```
```

Then it will show available applications

- NGINX Full
- NGINX HTTP
- OpenSSH
- NGINX HTTPS
 
It is recommended to enable the most restrictive profile. Since the SSL is not configured, allow non SSL traffic for now

 ```
<pre class="wp-block-code">```
sudo ufw allow 'Nginx HTTP'
```
```

Now verify the status

 ```
<pre class="wp-block-code">```
sudo ufw status
```
```

Next we need to verify installation status

 ```
<pre class="wp-block-code">```
systemctl status nginx
```
```

Use server’s IP address to to access the default NGINX landing page. Here are some methods to get server’s IP address

 ```
<pre class="wp-block-code">```
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```
```

Another way to get server’s public IP address is

 ```
<pre class="wp-block-code">```
curl -4 icanhazip.com
```
```

When you have your server’s IP address, enter it into your browser’s address bar:

 ```
<pre class="wp-block-code">```
http://your_server_ip
```
```

That’s it. NGINX is installed successfully.

#### Some Helpful Commands

Stop web server

 ```
<pre class="wp-block-code">```
sudo systemctl stop nginx
```
```

Start web server

 ```
<pre class="wp-block-code">```
sudo systemctl start nginx
```
```

Stop and then start the server

 ```
<pre class="wp-block-code">```
sudo systemctl restart nginx
```
```

Reload web server

 ```
<pre class="wp-block-code">```
sudo systemctl reload nginx
```
```

Disable and Enable NGINX

 ```
<pre class="wp-block-code">```
sudo systemctl disable nginx
```
```

To re-enable the service to start up at boot, you can type:

 ```
<pre class="wp-block-code">```
sudo systemctl enable nginx
```
```