---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Guide
------------------

### Installation using Github

Download WordPress from [Github](https://github.com/WordPress/WordPress)

1. Unzip the package in an empty directory and upload everything.
2. Open <span class="file">[wp-admin/install.php](#)</span> in your browser. It will take you through the process to set up a `wp-config.php` file with your database connection details. 
  1. If for some reason this doesn’t work, don’t worry. It doesn’t work on all web hosts. Open up `wp-config-sample.php` with a text editor like WordPad or similar and fill in your database connection details.
  2. Save the file as `wp-config.php` and upload it.
  3. Open <span class="file">[wp-admin/install.php](#)</span> in your browser.
3. Once the configuration file is set up, the installer will set up the tables needed for your site. If there is an error, double check your `wp-config.php` file, and try again. If it fails again, please go to the [WordPress support forums](https://wordpress.org/support/forums/) with as much data as you can gather.
4. **If you did not enter a password, note the password given to you.** If you did not provide a username, it will be `admin`.
5. The installer should then send you to the [login page](#). Sign in with the username and password you chose during the installation. If a password was generated for you, you can then click on “Profile” to change the password.
 
### Installation using Docker

#### Install the Docker packages with the apt command below:

 ```
apt-get install docker.io
```

When the installation has finished, start docker and add it to run at the system boot time with the systemctl command:

 ```
systemctl start docker
systemctl enable docker
```

Next, check the Docker version with this docker command:

 ```
docker version
docker run hello-world
```

#### Setup the MariaDB Container

In this step, we will download a new MariaDB images from the docker registry and create a new container based on that image. We will configure a new database and user for the WordPress installation.   
 Download the Docker MariaDB image to the system with the Docker pull command:

 ```
docker pull mariadb
```

Now you can see the new docker MariaDB image with the command below:

 ```
docker images
```

Next, create a new container from the MariaDB image for the WordPress installation. Before creating the new container, create a new directory for the WordPress data, database directory, and the WordPress code directory.

 ```
mkdir ~/wordpress
mkdir -p ~/wordpress/database
mkdir -p ~/wordpress/html
```

Now create the new MariaDB container with name 'wordpressdb' with the command below:

 ```
docker run -e MYSQL_ROOT_PASSWORD=aqwe123 -e MYSQL_USER=wpuser -e MYSQL_PASSWORD=wpuser@ -e MYSQL_DATABASE=wordpress_db -v /root/wordpress/database:/var/lib/mysql --name wordpressdb -d mariadb
```

TheMariaDBriadb container has been created, now check the new user and the database for the WordPress installation to ensure there is no error with command on top.   
 From the host machine, check the wordpressdb container IP address with docker command below:

 ```
docker inspect -f '{{ .NetworkSettings.IPAddress }}' wordpressdb
```

Next, connect to the wordpressdb container with mysql command from the host system:

 ```
mysql -u wpuser -h 172.17.0.2 -p 
TYPE PASSWORD: wpuser@
```

The new Docker container, MySQL user, and the MySQL database for WordPress have been successfully created.

#### Setup the Wordpress Container

Once the database container has been created, download the latest WordPress docker image with the docker pull command:

 ```
docker pull wordpress:latest
```

When the download has finished, create a new container from the images with the name 'wpcontainer'.

 ```
docker run -e WORDPRESS_DB_USER=wpuser -e WORDPRESS_DB_PASSWORD=wpuser@ -e WORDPRESS_DB_NAME=wordpress_db -p 8081:80 -v /root/wordpress/html:/var/www/html --link wordpressdb:mysql --name wpcontainer -d wordpress
```

To see the WordPress container running, you can check it with the curl command on the host IP and port 8081.

 ```
curl -I 192.168.43.99:8081
```

You will see the results:

- The web server is Apache, running on the Debian.
- PHP 5.6 is running in the container.
- You see the redirect to the WordPresss installation.
 