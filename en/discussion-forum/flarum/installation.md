---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Flarum on Ubuntu 18.04 LTS with Composer

You will need to install Apache, MariaDB and PHP to your system. First, install Apache and MariaDB using the following command:

 ```
<pre class="command">```
sudo apt-get install apache2 mariadb-server -y
```
```

Next, install PHP 7.1 to your system. But, PHP 7.1 is not available in Ubuntu 18.04 default repository. So you will need to add the repository for PHP first. You can add it with the following command:

 ```
<pre class="command">```
sudo apt-get install python-software-properties -y<br></br>sudo add-apt-repository -y ppa:ondrej/php
```
```

After installing PHP repository, install PHP7.1 along with all the required libraries using the following command:

 ```
<pre class="command">```
sudo apt-get install php7.1 libapache2-mod-php7.1 php7.1-common php7.1-mbstring php7.1-xmlrpc php7.1-soap php7.1-mysql php7.1-gd php7.1-xml php7.1-cli php7.1-zip wget unzip curl git -y
```
```

Next, you will also need to make some changes in php.ini file:

 ```
<pre class="command">```
sudo nano /etc/php/7.1/apache2/php.ini
```
```

Make the following changes:

 ```
file_uploads = On
allow_url_fopen = On
memory_limit = 256M
upload_max_file_size = 150M
max_execution_time = 450
```

Save and close the file, when you are finished. Then, start Apache and MariaDB service and enable them to start on boot with the following command:

 ```
<pre class="command">```
sudo systemctl start apache2<br></br>sudo systemctl start mysql<br></br>sudo systemctl enable apache2<br></br>sudo systemctl enable mysql
```
```

By default, the MariaDB is not secured. So you will need to secure it first. You can secure it by running the mysql\_secure\_installation script:

 ```
<pre class="command">```
mysql_secure_installation
```
```

Answer all the questions as shown below:

 ```
Enter current password for root (enter for none): Enter
Set root password? [Y/n]: Y
New password: 
Re-enter new password: 
Remove anonymous users? [Y/n]: Y
Disallow root login remotely? [Y/n]: Y
Remove test database and access to it? [Y/n]: Y
Reload privilege tables now? [Y/n]: Y
```

Next, log into MariaDB shell with the following command:

 ```
<pre class="command">```
mysql -u root -p
```
```

Enter your root password, then create a Flarum database:

 ```
<pre class="command">```
CREATE DATABASE flarumdb;
```
```

Next, create a Flarum user with the following command:

 ```
<pre class="command">```
GRANT ALL PRIVILEGES ON flarumdb.* TO 'flarum'@'localhost' IDENTIFIED BY 'password';<br></br>FLUSH PRIVILEGES;<br></br>EXIT
```
```

Next, you will need to install Composer to your system. You can install Composer with the following command:

 ```
<pre class="command">```
sudo curl -s https://getcomposer.org/installer | php<br></br>sudo mv composer.phar /usr/local/bin/composer
```
```

Next, create a directory under Apache web root for Flarum project and install via Composer:

 ```
<pre class="command">```
sudo mkdir /var/www/html/flarum<br></br>cd /var/www/html/flarum<br></br>sudo composer create-project flarum/flarum . --stability=beta<br></br>sudo chown -R www-data:www-data /var/www/html/flarum/<br></br>sudo chmod -R 755 /var/www/html/flarum/
```
```

Next, create an apache virtual host directive for Flarum:

 ```
<pre class="command">```
sudo nano /etc/apache2/sites-available/flarum.conf
```
```

Add the following lines:

 ```
<pre class="command">```
<VirtualHost *:80>
 ServerAdmin <span id="cloak3bc6d11fedcd265aba5e552d898610c8">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak3bc6d11fedcd265aba5e552d898610c8').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy3bc6d11fedcd265aba5e552d898610c8='&#97;dm&#105;n'+'&#64;';addy3bc6d11fedcd265aba5e552d898610c8=addy3bc6d11fedcd265aba5e552d898610c8+'y&#111;&#117;rd&#111;m&#97;&#105;n'+'&#46;'+'c&#111;m';var addy_text3bc6d11fedcd265aba5e552d898610c8='&#97;dm&#105;n'+'&#64;'+'y&#111;&#117;rd&#111;m&#97;&#105;n'+'&#46;'+'c&#111;m';document.getElementById('cloak3bc6d11fedcd265aba5e552d898610c8').innerHTML+='<a '+path+'\''+prefix+':'+addy3bc6d11fedcd265aba5e552d898610c8+'\'>'+addy_text3bc6d11fedcd265aba5e552d898610c8+'<\/a>';</script>
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
```
```

Save and close the file, then enable virtual host file and rewrite module with the following command:

 ```
<pre class="command">```
sudo a2ensite flarum <br></br>sudo a2enmod rewrite
```
```

Finally, restart Apache web server to apply all the changes. Open your web browser and nevigate to URL http://yourdomain.com to access Flarum.

### Installation using Docker

Pull Flarum Image from hub.docker.com:

 ```
<pre class="command">```
docker pull mondedie/flarum:latest
```
```

Configure Docker-compose.yml:

 ```
<pre class="command">```
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

```
```

Create an environment file:

 ```
<pre class="command">```
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
FLARUM_ADMIN_MAIL=<span id="cloaka095faba38f31e457512219529fbcb61">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloaka095faba38f31e457512219529fbcb61').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addya095faba38f31e457512219529fbcb61='&#97;dm&#105;n'+'&#64;';addya095faba38f31e457512219529fbcb61=addya095faba38f31e457512219529fbcb61+'d&#111;m&#97;&#105;n'+'&#46;'+'tld';var addy_texta095faba38f31e457512219529fbcb61='&#97;dm&#105;n'+'&#64;'+'d&#111;m&#97;&#105;n'+'&#46;'+'tld';document.getElementById('cloaka095faba38f31e457512219529fbcb61').innerHTML+='<a '+path+'\''+prefix+':'+addya095faba38f31e457512219529fbcb61+'\'>'+addy_texta095faba38f31e457512219529fbcb61+'<\/a>';</script>
FLARUM_TITLE=Test flarum

```
```

Run your docker-compose:

 ```
<pre class="command">```
docker-compose up -d mariadb
docker-compose up -d flarum

```
```

Congrats! You have successfully installed Flarum