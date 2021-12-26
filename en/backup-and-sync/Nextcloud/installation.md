---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Nextcloud On Ubuntu**

First, ensure that all the depency packages of Nextcloud open source file storage are installed and up to date. The following instructions are using /var/www as the web server’s directory. www-data is the user name and group name. After the development tool installation make the directory writable so you install the code as your regular user. You don’t need root privileges to setup. Please follow the instructions listed below:

    sudo chmod o+rw /var/www

Next, clone the source code and install Nextcloud application at the root of your site :

    git clone https://github.com/nextcloud/server.git /var/www/
    cd /var/www
    git submodule update --init

If you prefer to install Nextcloud in a subfolder then replace /var/www with /var/www/<folder>. Create the data folder with:

    cd /var/www
    mkdir data

Apply the required permissions by following:

    cd /var/www
    sudo chown -R www-data:www-data config data apps
    sudo chmod o-rw /var/www

Finally, restart the Web server and it may vary depending on your distribution:

    sudo systemctl restart httpd.service

or by:

    sudo systemctl restart apache2.service

or by:

    sudo /etc/init.d/apache2 restart

Now you can access the installation at http://localhost/ or the corresponding URL in your web browser to set up your instance. Once you have a Nextcloud home server running on your host, you can connect to it with various clients like mobile or desktop clients.

Congratulations! You have now set up the Nextcloud file sharing collaboration software. Enjoy!
