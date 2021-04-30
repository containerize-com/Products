---
title: Installation
onpagelink: installation
weight: 3

---
Installation
------------

### Ubuntu Installation:

Installation of phpMyAdmin is very simple and straight-forward. Follow these step to install phpMyAdmin on Ubuntu:

*   Open a terminal window on your Ubuntu Server.
*   Then issue the command.

       
       
       
        apt update && apt upgrade

*   And then this command.

                        
                        
        sudo apt-get install phpmyadmin php-mbstring php-gettext -y

*   After that a window will open up, type your sudo password.
*   Then Allow the installation to complete.
*   Select the web server to be used as shown in following figure

![Open Source Database Management Tool for MySQL & MariaDB](/images/phpmyadmin_installation_steps.png "Open Source Database Management Tool for MySQL & MariaDB")

*   Next set a MySQL application password for phpmyadmin
*   And then enter the database admin user password.

![Open Source Database Management Tool for MySQL & MariaDB](/images/phpmyadmin_installation_steps_2.png "Open Source Database Management Tool for MySQL & MariaDB")

*   After that restart the server.

                        
                        
         systemctl restart apache2
    

*   Finally Login to phpMyAdmin from this URL: [http://server\_ip/phpmyadmin](http://server_ip/phpmyadmin)

### Windows Installation:

*   Go to phpMyAdmin [download](https://www.phpmyadmin.net/downloads/) [page](https://www.phpmyadmin.net/downloads/).
*   Then click on “Download” button.
*   After that, open and extract the downloaded zip folder.
*   Copy phpmyadmin folder to c drive -> htdocs.
*   Now open php.ini file to edit it.
*   Then search for “extension=php\_mbstring.dll” line and replace “;” from the start.
*   Now search for “extension=php\_mysqli.dll” line and replace “;” from the start.
*   Save and exit.
*   Restart “Apache” service.
*   Finally Login to phpMyAdmin from this URL: [http://server\_ip/phpmyadmin](http://server_ip/phpmyadmin)