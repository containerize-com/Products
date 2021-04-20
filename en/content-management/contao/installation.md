---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

After you have checked all requirements and set up your web server, you can now start the installation.

There are two ways to install Contao on your server, using the graphical user interface of the ContaoManager or using the command line.

### Installing Contao with the Contao Manager

After the successful basic configuration, you can now install Contao. Select the desired version and the initial configuration and click the “Finish” button.

The installation can now take several minutes. Details about the installation process can be displayed by clicking the following iconShow/Hide Console Output.

#### Update database tables

Once the Contao Manager has installed all packages, you have to run the Contao install tool to update the database.

### Installation via the command line {#installation-over-the-command line}

When installing from the command line, `create-projecta` `composer update` command is executed during the installation. This will cause some hosters not to be able to terminate the process due to high system load, and the installation will fail. In this case you should use the Contao Manager.

You have logged on to your server with your user name and domain.

 ```
ssh <span id="cloak07368bd751c5cfef1fcfd23c2ee570b0">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak07368bd751c5cfef1fcfd23c2ee570b0').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy07368bd751c5cfef1fcfd23c2ee570b0='b&#101;n&#117;tz&#101;rn&#97;m&#101;'+'&#64;';addy07368bd751c5cfef1fcfd23c2ee570b0=addy07368bd751c5cfef1fcfd23c2ee570b0+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text07368bd751c5cfef1fcfd23c2ee570b0='b&#101;n&#117;tz&#101;rn&#97;m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak07368bd751c5cfef1fcfd23c2ee570b0').innerHTML+='<a '+path+'\''+prefix+':'+addy07368bd751c5cfef1fcfd23c2ee570b0+'\'>'+addy_text07368bd751c5cfef1fcfd23c2ee570b0+'<\/a>';</script>
```

Change to the public directory of your web hosting.

 ```
cd www
```

#### Install Composer

Composer is an application-oriented package manager for the PHP programming language and installs dependencie

#### Installing Contao from the command line

In the second step, you install Contao using the Composer. “example” stands for the desired installation directory and 4.8 for the version of Contao you want to install.

 ```
php composer.phar create-project contao/managed-edition example 4.8
```

#### Hosting Configuration

In Contao, all publicly accessible files are located in the subfolder `/web` of the installation. Use the admin panel of the hosting provider to set the document root of the installation to this subfolder and create a database on this occasion.

Example: `example.com` points to the directory `/www/example/web`

#### Update database tables

After installation, you can update the database using the Contao install tool.

Since Contao 4.9 you can use the following command on the command line:

 ```
php vendor/bin/contao-console contao:migrate
```

#### Creating Contao back end users

Using the Contao-Installtool, you can create your back end user. Since Contao 4.10 you can use the following command on the command line:

 ```
php vendor/bin/contao-console contao:user:create
```