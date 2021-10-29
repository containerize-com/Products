---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Once pre-requisites are installed, run the following command to clone the source code:

     git clone https://github.com/nextcloud/server.git

Then, run the following commands:

    cd /var/wwwgit submodule update --init

If you prefer to install Nextcloud in a sub-folder, replace /var/www with /var/www/<folder>.

After that, create the data folder:

    cd /var/wwwmkdir data

After that, run the following commands to adjust permissions:

    cd /var/wwwsudo chown -R www-data:www-data config data appssudo chmod o-rw /var/www

Lastly, restart the Web serve:

    sudo systemctl restart httpd.service

Finally, access the application at http://localhost/.

