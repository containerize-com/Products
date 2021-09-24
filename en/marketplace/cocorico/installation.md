---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions to setup the production environment
-----------------------------------------------------------------

### Installation on Ubuntu

Install and configure the necessary dependencies packages. Fork Cocorico git repository then get sources. Go to to your parent 'Document Root' directory and clone repository:

 ```
cd /var/www/cocorico.dev/
git clone https://github.com/Cocolabs-SAS/cocorico.git Symfony
```

Create services Google API, microsoft Translator and Facebook Login App accounts by following guides from here:

 ```
https://console.developers.google.com/project
https://www.microsoft.com/translator/getstarted.aspx. 
https://developers.facebook.com/docs/apps/register
```

Now install composer. If you don't have Composer yet, run the following command in the root folder of your Symfony project:

 ```
cd Symfony
curl -s http://getcomposer.org/installer | php
```

Install Cocorico dependencies and below command will ask you the values of some of your application parameters:

 ```
php composer.phar install --prefer-dist -vvv
```

Set your application parameters:

 ```
app/config/parameters.yml.dist
```

Configure environment defaults. Copy and paste web/.htaccess.dist and rename it to web/.htaccess. Initialize the SQL and NoSQL MongoDB database:

 ```
chmod 744 bin/init-db
./bin/init-db php --env=dev
chmod 744 bin/init-mongodb
./bin/init-mongodb php --env=dev
```

Before starting coding, execute this script to make sure that your local system is properly configured for Cocorico:

 ```
php bin/symfony_requirements
```

The script returns a status code of 0 if all mandatory requirements are met, 1 otherwise. Access the config.php script from a browser: http://localhost:8080/config.php If you get any warnings or recommendations, fix them before moving on. Now check security dependencies:

 ```
bin/security-checker security:check composer.lock
```

In case of error "An error occurred: SSL certificate problem: unable to get local issuer certificate, run below

 ```
bin/security-checker security:check --end-point=http://security.sensiolabs.org/check_lock composer.lock
```

Dump the assets

 ```
php bin/console assets:install --symlink web --env=dev
php bin/console assetic:dump --env=dev
```

You need to configure a couple Cron jobs in order to properly run your marketplace in production. See the [Crons documentation](https://github.com/Cocolabs-SAS/cocorico/blob/master/doc/crons.md). You can read about Cocorico features in more detail on the platform’s site, but the idea here is that Cocorico has everything our clients typically ask for.

Congratulations! You have successfully installed Cocorico marketplace. Enjoy!
