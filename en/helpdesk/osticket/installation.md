---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

Updating packages on your system to the latest release.

 ```
sudo apt-get update<br></br>sudo apt-get upgrade 
```

On Ubuntu, you can install Apache Web server from the official apt repository:

 ```
sudo apt install apache2 
```

To start the service manually, run:

 ```
 sudo systemctl start apache2
```

Though the service is enabled to start on boot by default, manually allowing it you have to run:

 ```
 sudo systemctl enable apache2
```

Next, need to install database Server, use the following command to install MySql server

 ```
 sudo apt-get update;  sudo apt-get install mysql-server; mysql_secure_installation 
```

Once, the database server is installed, use the following command to restart MySql server

 ```
 sudo service mysql restart 
```

The next step is the to install PHP on Ubuntu:

 ```
sudo apt update
sudo apt-get install php php-{fpm,pear,imap,apcu,intl,cgi,common,mbstring,net-socket,gd,xml-util,mysql,bcmath}

```

Now, you have installed all the required software and the next step is to login to mysql server and create osTicket database. Use following command to create database. Change with your database name.

 ```
 CREATE DATABASE  
```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Next, run the commands below to download and extract the downloaded file and move it into a new osTicket root directory.

 ```
sudo apt-get install curl wget unzip
curl -s https://api.github.com/repos/osTicket/osTicket/releases/latest \
  | grep browser_download_url \
  | grep "browser_download_url" \
  | cut -d '"' -f 4 \
  | wget -i -
ls osTicket
scripts  upload
sudo mv osTicket /var/www/
cd /var/www/osTicket/upload/include
sudo cp ost-sampleconfig.php ost-config.php
sudo chown -R www-data:www-data /var/www/

```

Create a database user called "" with new password. and granted user full access to the database by running the following commands. Change with your desired database user and with your desired password.

 ```
 CREATE USER ''@'localhost' IDENTIFIED BY ''; 
 GRANT ALL ON .* TO ''@'localhost' IDENTIFIED BY '' WITH GRANT OPTION;
 FLUSH PRIVILEGES; EXIT;
```

Create VirtualHost configuration file for osTicket on Apache configurations directory:

 ```
 sudo vim /etc/apache2/sites-enabled/osticket.conf

```

Add content:

 ```
ServerAdmin <span id="cloak93afa25b2e40fbb9f227d2cb467426bc">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak93afa25b2e40fbb9f227d2cb467426bc').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy93afa25b2e40fbb9f227d2cb467426bc='&#97;dm&#105;n'+'&#64;';addy93afa25b2e40fbb9f227d2cb467426bc=addy93afa25b2e40fbb9f227d2cb467426bc+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text93afa25b2e40fbb9f227d2cb467426bc='&#97;dm&#105;n'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak93afa25b2e40fbb9f227d2cb467426bc').innerHTML+='<a '+path+'\''+prefix+':'+addy93afa25b2e40fbb9f227d2cb467426bc+'\'>'+addy_text93afa25b2e40fbb9f227d2cb467426bc+'<\/a>';</script>
DocumentRoot /var/www/osTicket/upload
ServerName osticket.example.com
ServerAlias www.osticket.example.com
Options FollowSymlinks
AllowOverride All
Require all granted
ErrorLog ${APACHE_LOG_DIR}/osticket_error.log
CustomLog ${APACHE_LOG_DIR}/osticket_access.log combined

```

Restart apache2:

 ```
sudo systemctl restart apache2
```

### Installation using Docker

Pull osTicket Image from hub.docker.com:

 ```
docker pull osticket/osticket
```

Make sure you have a MySQL container running that osTicket can use to store its data.

 ```
docker run --name osticket_mysql -d -e MYSQL_ROOT_PASSWORD=secret \
-e MYSQL_USER=osticket -e MYSQL_PASSWORD=secret -e MYSQL_DATABASE=osticket mariadb
```

Now run this image and link the MySQL container.

 ```
docker run --name osticket -d --link osticket_mysql:mysql -p 8080:80 osticket/osticket
```

Once installation is completed then browse to your osTicket staff control panel at http://localhost:8080/scp. Login with default admin user &amp; password:

- username: ostadmin
- password: Admin1
 
Congrats! You have successfully installed osTicket on Apache.