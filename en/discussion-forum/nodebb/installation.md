---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installation using Github

Make sure you have installed Node.js, Redis / MangoDB and Nigix / IIS before installing the NodeBB.

Create a document root directory where NodeBB should locate in:

 ```
sudo mkdir -p /var/www/nodebb
 ```

Route to the document root directory:

 ```
cd /var/www/nodebb
 ```

Change ownership of the /var/www/nodebb directory to your\_user. Replace your\_user in the above command with your user.

 ```
sudo chown -R [your_user]:[your_user] /var/www/nodebb
 ```

Clone the latest NodeBB repository into document root folder:

 ```
git clone -b v1.15.x https://github.com/NodeBB/NodeBB.git .
 ```

Execute the setup script by running the app with the setup flag:

 ```
./nodebb setup
 ```

Input your answers to setup script, after NodeBB setup is completed, run ./nodebb start to manually start your NodeBB server:

 ```
./nodebb start
 ```

Congrats! You have successfully installed NodeBB. Now you can access your brand new forum in web browser.