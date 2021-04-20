---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Vanilla on Ubuntu having NGNIX

Create a document root directory where Vanilla Forum should reside in:

 ```
sudo mkdir -p /var/www/vanilla
```

Change ownership of the /var/www/vanilla directory to {your\_user}:

 ```
sudo chown -R {your_user}:{your_user} /var/www/vanilla
```

Navigate to the document root directory:

 ```
cd /var/www/vanilla
```

Download the Vanilla Forum zip archive:

 ```
wget https://open.vanillaforums.com/get/vanilla-core-2.6.4.zip
```

Extract and remove Vanilla zip archive:

 ```
unzip vanilla-core-2.6.4.zip
rm vanilla-core-2.6.4.zip
```

Provide the appropriate ownership:

 ```
sudo chown -R www-data:www-data /var/www/vanilla
```

Navigate to the folder where you uploaded Vanilla in your web browser and follow the instructions on the screen.

### Installation using Docker

Vanilla docker only supports Mac OSX at the moment.

Clone vanilla/vanilla-docker into your project directory.

 ```
git clone https://github.com/vanilla/vanilla-docker.git
```

Clone vanilla/vanilla into your project directory.

 ```
git clone https://github.com/vanilla/vanilla.git
```

You should have the following structure

 ```
my-vanilla-project
├── vanilla
├── vanilla-docker
├── ...
```

Move into the vanilla directory.

 ```
cd vanilla
```

Run composer install which will install Vanilla's dependencies.

Move up and over into the vanilla-docker directory.

 ```
cd ..
cd vanilla-docker
```

Run sudo ./mac-setup.sh which will:

- Add a self signed certificate \*.vanilla.localhost to your keychain.
- Safely update your /etc/hosts.
- Add 192.0.2.1 as a loopback IP address.
- Create a docker volume named "datastorage" which will contain the database data.
 
Run docker-compose up --build (It will take a while the first time). You'll know it worked if you see something like

 ```
Successfully built…
Successfully tagged…
Creating database ... done
Creating php-fpm ... done
Creating httpd ... done
Creating nginx ... done
Attaching to database, php-fpm, httpd, nginx
…
php-fpm | done.
```

dev.vanilla.localhost shows the Vanilla installer. Run the installer!

Run docker-compose up --build to start up the services

Well done! You have installed Vanilla successfully.