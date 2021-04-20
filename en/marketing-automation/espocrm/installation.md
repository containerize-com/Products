---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

First make sure you have installed all the dependencies. Then clone the latest EspoCRM repository into document root folder:

 ```
<pre class="command">```
git clone https://github.com/espocrm/espocrm
cd espocrm
```
```

Set appropriate permissions for directories and files

 ```
<pre class="command">```
find . -type d -exec chmod 755 {} + && find . -type f -exec chmod 644 {} +;
find data custom client/custom -type d -exec chmod 775 {} + && find data custom client/custom -type f -exec chmod 664 {} +;
chmod 775 application/Espo/Modules client/modules;

```
```

All files should be owned and group-owned by the webserver process. It can be www-data, daemon, apache, www, etc.

 ```
<pre class="command">```
cd <PATH-TO-ESPOCRM-DIRECTORY> 
chown -R <OWNER>:<GROUP-OWNER> .;

```
```

Now open your web browser and type the URL below to access the EspoCRM web installer wizard. http://yourdomain.com/espo

Follow the installation wizard steps. Your EspoCRM website is ready.