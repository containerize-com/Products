---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installation for Master Branch &amp; Future Version

- Download and unzip inoerp into your server. The first folder contains 2 different folders: inoerp\_server and www. Copy the contents of www folder to your web folder (www or htdocs). Put the inoerp\_server a directory above the web folder.
- Change the DB settings @ include\\basics\\settings\\dbsettings.inc , and Change the session\_set\_cookie\_params in sessions file
- Open the index.php /or install.php page and follow the simple four steps installation process (mySQL user must have all the privileges equivalent to root a user to create views. You can change to a lesser privileged user after installation by changing the username &amp; password @ include\\basics\\dbsettings.inc)
- Login into the application using user id /password - inoerp/inoerp
 
### Auto Installation

- Upload all the files on the web server
- If using Apache then enable mod\_rewrite module before you proceed further
- Open the index.php /or install.php page and follow the simple four steps installation process (mySQL user must have all the privileges equivalent to root a user to create views. You can change to a lesser privileged user after installation by changing the username &amp; password @ include\\basics\\dbsettings.inc)
- Login into the application using user id /password - inoerp/inoerp
 
### Manual Installation

- Change the DB settings @ include\\basics\\settings\\dbsettings.inc
- Change the session\_set\_cookie\_params in sessions file
- Import the database file @ enine\\install\\inoerp.sql
- Change the .htaccess
- Login in to the application using user id /password - inoerp/inoerp
 