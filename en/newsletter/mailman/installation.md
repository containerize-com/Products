---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Install Postfix SMTP server

Install SMTP server such as Postfix by following guideline.

[How to install and configure Postfix SMTP server](https://products.containerize.com/transactional-email/postfix)

#### Install GNU Mailman

Install GNU Mailman from repository.

 ```
sudo apt install mailman
```

Run this command for creating mailman list.

 ```
sudo newlist mailman
```

Enter admin email address and set a password, then edit /etc/aliases file by using below command.

 ```
sudo nano /etc/aliases
```

Copy and paste the following lines into the file.

 ```

## mailman mailing list
mailman:              "|/var/lib/mailman/mail/mailman post mailman"
mailman-admin:        "|/var/lib/mailman/mail/mailman admin mailman"
mailman-bounces:      "|/var/lib/mailman/mail/mailman bounces mailman"
mailman-confirm:      "|/var/lib/mailman/mail/mailman confirm mailman"
mailman-join:         "|/var/lib/mailman/mail/mailman join mailman"
mailman-leave:        "|/var/lib/mailman/mail/mailman leave mailman"
mailman-owner:        "|/var/lib/mailman/mail/mailman owner mailman"
mailman-request:      "|/var/lib/mailman/mail/mailman request mailman"
mailman-subscribe:    "|/var/lib/mailman/mail/mailman subscribe mailman"
mailman-unsubscribe:  "|/var/lib/mailman/mail/mailman unsubscribe mailman"

```

Run following command to update the alias index file.

 ```
sudo newaliases
```

Run below command to restart Postfix SMTP server.

 ```
sudo systemctl restart postfix
```

Run below command to start the Mailman program.

 ```
sudo systemctl start mailman
```

### Install FCGIWrap

For Mailman web interface, install fcgiwrap package that allows to run CGI applications with FastCGI and Nginx.

 ```
sudo apt install fcgiwrap
```

Make sure FCGI and Nginx run as the same user (www-data). Edit the /etc/init.d/fcgiwrap by running below command.

 ```
sudo nano /etc/init.d/fcgiwrap
```

Set www-data value for FCGI\_USER and FCGI\_GROUP variables

 ```

FCGI_USER="www-data"
FCGI_GROUP="www-data"

```

Restart fcgiwrap service

 ```
sudo systemctl restart fcgiwrap
```

### Install Nginx

Run below command to install Nginx.

 ```
sudo apt install nginx
```

Restart fcgiwrap service

 ```
sudo systemctl restart fcgiwrap
```

Edit the server block file of your website

 ```
sudo nano /etc/nginx/sites-available/your-site.conf
```

Add following lines in the server section.

 ```

location /cgi-bin/mailman {
       root /usr/lib/;
       fastcgi_split_path_info (^/cgi-bin/mailman/[^/]*)(.*)$;
       include /etc/nginx/fastcgi_params;
       fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
       fastcgi_param PATH_INFO $fastcgi_path_info;
       fastcgi_param PATH_TRANSLATED $document_root$fastcgi_path_info;
       fastcgi_intercept_errors on;
       fastcgi_pass unix:/var/run/fcgiwrap.socket;
}
location /images/mailman {
       alias /usr/share/images/mailman;
}
location /pipermail {
       alias /var/lib/mailman/archives/public;
       autoindex on;
}

```

Restart Nginx web server.

 ```
sudo systemctl reload nginx
```

Open below URL in browser to access admin panel.

 ```
http://www.your-site.com/cgi-bin/mailman/admin/
```
