---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

Once you have installed the pre-requisites, run the  following commands to install all required packages:

 ```
yum groupinstall "Development Tools" "Development Libraries"
yum -y install gcc-c++ git ruby ruby-devel rubygems \ libvirt-devel postgresql-devel openssl-devel \ libxml2-devel libxslt-devel zlib-devel \ readline-devel systemd-devel tar nodejs npm libcurl-devel
```

It is important that config/database.yml is set to use the correct database in the “production” block.

Now, run the following command to clone the source code:

 ```
git clone https://github.com/theforeman/foreman.git -b develop
```
After that, run these commands for the configurations:

 ```
cp config/settings.yaml.example config/settings.yaml
cp config/database.yml.example config/database.yml
gem install bundler
```
Then, run the following command to install dependencies:

 ```
bundle install --without development test --path vendor
npm install
```
Following commands will set up database schema:

 ```
RAILS_ENV=production bundle exec rake db:migrate
RAILS_ENV=production bundle exec rake db:seed assets:precompile locale:pack webpack:compile
```
Finally, you can run the application using the following command:

 ```
./bin/rails s -e production
```
