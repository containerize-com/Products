---
title: Installation Guide
onpagelink: installation
weight: 3

---
### **Installation**

### Install FatFreeCRM on Linux (Debian-based)

FatFreeCRM below instructions only work for 64 bit Debian-based Linux distributions such as Ubuntu. Grab a copy of FatFreeCRM from GitHub

    git clone git@github.com:fatfreecrm/fat_free_crm.git fat_free_crm

Change current working directory to previously created one

    cd fat_free_crm

Fat Free CRM supports MySQL database. The source code comes with sample database configuration files. You will need to copy the config for your chosen db:

    cp config/database.mysql.yml config/database.yml

Edit config/database.yml and specify database names and authentication details. You may need to install some platform specific libraries to satisfy all the gem dependencies.

    sudo apt-get install libmagick++-dev libxml2 libxml2-dev libxslt1.1 libxslt1-dev libyaml-dev
    sudo apt-get install mysql-client libmysqlclient-dev

If you have trouble installing the DB dependencies, you will need to refer to the MySQL documentation for installation on your platform, before continuing. Once the above is complete, run the following command from the application’s root directory:

    bundle install

Now you are ready to create the database:

    rake db:create

You can configure Fat Free CRM settings, such as your host, base URL, language (locale), menu structures, default colors, and email authentication. Fat Free CRM settings are stored in three places, and are loaded in the following order:

    config/settings.default.yml
    config/settings.yml (if exists)
    ‘settings’ table in database (if exists)

Settings loaded last have the highest priority, and override any settings from the previous sources. Run database migrations and set up an admin user Run the following rake task:

    rake ffcrm:setup

The previous command will migrate the database and prompt you for an admin user name, password and email. You can test drive Fat Free CRM by loading sample records that are generated on the fly mimic the actual use. Loading demo will delete all existing data from your database.

    rake ffcrm:demo:load

Now you should be able to launch the Rails server and point your web browser to http://localhost:3000

    rails server

Congratulations! You have successfully installed FatFreeCRM application.
