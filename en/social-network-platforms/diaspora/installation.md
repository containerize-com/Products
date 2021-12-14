---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Run the following command to install the packages
 ```
yum install tar make automake gcc gcc-c++ git net-tools cmake libcurl-devel libxml2-devel libffi-devel libxslt-devel wget redis ImageMagick nodejs libpq-devel
```
Run the following commands to setup user for Diaspora
 ```
adduser diaspora chmod 755 /home/diaspora su - diaspora cd ~
```
After that, create a user with the privilege to create databases.
 ```
CREATE USER diaspora WITH CREATEDB PASSWORD '<password>';
```
Once all the pre-requisites are installed, run the following command to clone the source code.
 ```
cd ~
git clone -b master https://github.com/diaspora/diaspora.git
cd diaspora
```
Copy the configuration files 
 ```
cp config/database.yml.example config/database.yml
cp config/diaspora.toml.example config/diaspora.toml
```
username: Make sure to use the right username you created for diaspora.
password: Make sure to use the right password for the user your created for diaspora.

You can visit [this](https://wiki.diasporafoundation.org/Installation/CentOS/8) page for further configurations.

Then, run the following commands to install the Ruby libraries required.
 ```
gem install bundler
script/configure_bundler
bin/bundle install --full-index
RAILS_ENV=production bin/rake assets:precompile
```
Finally, start the server by running the following command
 ```
./script/server
```
