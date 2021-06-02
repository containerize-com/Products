---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installation using Github

Make sure you have installed PHP, Supported Database and Nigix / IIS before installing the phpBB.

Create a document root directory where NodeBB should locate in:

Clone the latest phpBB repository into document root folder:

 ```
git clone https://github.com/phpbb/phpbb.git
 ```

Navigate to phpBB directory

 ```
cd phpBB
 ```

Run the following commands to install phpBB's dependencies

 ```
php ../composer.phar install
 ```

After running this command, you should be able to access phpBB Web Installer in your browser. Now follow the web installer steps and you have installed the phpBB.