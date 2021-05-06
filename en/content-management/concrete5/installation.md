---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installing concrete5 On a Web Host

To get started, you will need a hosting environment. For most people, this means buying a hosting plan. Concrete5 will run just about anywhere, but we do have some hosting partners worth checking out. You can also do local development with Concrete5 by installing the various required components and starting a local web server.

1. [Download](https://www.concrete5.org/download) the latest version of Concrete5.
2. Move or upload that zip file to your web server or your web environment. You'll want to unzip the file in a web-accessible folder in your webspace. Usually this folder is public\_html. If you want to run Concrete5 in a subdirectory, you can create a new folder like "new-site" and unzip your Concrete5 files in there.
3. After you unzip the file, it will add some new folders and an index.php.
4. The folders application/files/, application/config/, packages/ and updates/ will need to be writable by the web server process. This can mean that the folders will need to be "world writable", depending on your hosting environment. If your server supports running as suexec/phpsuexec, the files should be owned by your user account, and set as 755 on all of them. That means that your web server process can do anything it likes to them, but nothing else can (although everyone can view them, which is expected.) If this isn't possible, another good option is to set the apache user (either "apache" or "nobody") as having full rights to these file. If neither are possible, chmod 777 to files/ and all items within (e.g. chmod -R 777 files/\*)
5. Create a new MySQL database and a MySQL user account with full permissions on the database. Make a note of your database server (usually "localhost") as well as the database name, and the name and password for the database user that has access to that database.
6. Visit your site, "http://example.com", or "http://example.com/new-site/" if you extracted the concrete5 zip into a folder called "new-site". You will see a helpful install screen like this:
 
### Installing concrete5 with Composer and the Command Line

More versatile and maintanable than simply downloading a zip file from concrete5.org, Composer is a better way to install concrete5. Before you begin this process, you’ll need to have a local development environment available on your development machine, and you’ll need to know how to configure it. This development environment needs to conform to the minimum system requirements of concrete5. It will need PHP and MySQL installed and running, and you’ll need to know how to access them via the command line. This guide may touch on some of these topics, but if any of them are wholly unfamiliar you’ll need to do some additional reading.

#### Create a Directory for Your Site

First, create a directory for your site in the directory where your development sites are normally installed. I’m going to create a site named “Hello World”. First, let’s create a database for your Hello World application. Run the mysql client with a user capable of creating a database (such as root) and create a Hello World database:

 `create database hello_world`Exit out of MySQL back to the hello-world directory. Now, we’re going to install concrete5 via composer. (Note: this guide assumes you have composer installed on your development machine. If you don’t, you’ll need to head to http://getcomposer.org/ and install composer from there.)

 `composer create-project -n concrete5/composer hello_world`This will install concrete5 and its PHP dependencies in a directory named hello-world.

### Installing concrete5 via the Command Line Utility

Now it’s time to install concrete5. Let’s use concrete5’s interactive installation command line utility:

 ```
cd hello-world`
./vendor/bin/concrete5 c5:install -i
```

Enter the configuration details of your local database and your local site, and press Enter. Installation should be complete in less than a minute:

### Accessing Our Site

Now that we’ve installed concrete5, let’s browse it. In a production environment you’d want to configure a web server like Apache or Nginx to serve this content – but that’s not necessary in our development environment. Instead, let’s get going quickly by using PHP’s built-in web server to launch and serve and the contents our hello\_world directory. First, change into the public/ directory and run this command from within the directory:

 ```
cd public
php -S localhost:8000
```

This should get you a fully functioning server in a matter of seconds. Next, visit http://localhost:8000 in your web browser.

You now have a fully functioning concrete5 site, tied to a local development environment! Now that concrete5 is up and running, let’s take a quick tour to familiarize (or re-familiarize) ourselves with the setup, features and functionality that concrete5 delivers.