---
title: Installation Guide
onpagelink: installation
weight: 3

---


#### **Installation Instructions**

These installation instructions are for macOS with Lion Server.

Firstly, edit the php.ini as mentioned below:

    short_open_tag = Onmax_execution_time = 60max_input_time = 90post_max_size = 30Mupload_max_filesize = 30MCheck:memory_limit = 128Mdisplay_errors = Offlog_errors = Onregister_globals = Offfile_uploads = On

Now, open the terminal and run the following commands:

    mysql -u root -pmysql> DROP DATABASE test;mysql> DELETE FROM mysql.user WHERE user = '';mysql> FLUSH PRIVILEGES;mysql>quit;

Create a plain text file named openemr.conf, insert the following data:

    <Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/documents>order deny,allowDeny from all</Directory><Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/edi>order deny,allowDeny from all</Directory><Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/era>order deny,allowDeny from all</Directory>

After that, save it on the desktop and move it to /private/etc/apache2/sites in the terminal. y running the following command:

    sudo cp -p ~/Desktop/openemr.conf /etc/apache2/sites/openemr.conf

Then, in the Finder: Go->Go to Folder->/Library/Server/Web/Data/Sites/Get Info for DefaultChange Sharing & Permissions so all groups can Read & Write, remember what it was to put it back later.Download, expand and move openemr-4.1.0 to /Library/Server/Web/Data/Sites/DefaultIn terminal:

    cd /Library/Server/Web/Data/Sites/Default
    ln -s openemr-4.1.0 openemr
    cd openemr
    sudo chmod 666 library/sqlconf.php
    sudo chmod 666 interface/globals.php
    sudo chown -R _www:_www sites
    sudo chown -R _www:_www library/freeb
    sudo chown -R _www:_www gacl/admin/templates_c
    sudo chown -R _www:_www interface/main/calendar/modules/PostCalendar/pntemplates/cache
    sudo chown -R _www:_www interface/main/calendar/modules/PostCalendar/pntemplates/compiled

Finally, open up web-browser and point it to the installation script at [http://localhost/openemr/setup.php](http://localhost/openemr/setup.php)
