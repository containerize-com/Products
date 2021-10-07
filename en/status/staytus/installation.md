---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing on Ubuntu 16.04

First install Ruby, Node.js and MySQL by following these commands.

 ```

$ sudo apt update
$ sudo apt install mysql-server ruby ruby-dev nodejs git build-essential libmysqlclient-dev
$ sudo gem install bundler procodile

```

Create a database and a user in your MySQL database.

 ```

CREATE DATABASE `staytus` CHARSET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER `staytus`@`localhost` IDENTIFIED BY 'choose-a-password';
GRANT ALL ON `staytus`.* TO `staytus`@`localhost`;

```

Create system user for Staytus.

 ```
$ sudo useradd -r -d /opt/staytus -m -s /bin/bash staytus
```

Downloading the Staytus from GitHub repository.

 ```
$ sudo -u staytus git clone https://github.com/adamcooke/staytus /opt/staytus/staytus
```

Change directory by using below command.

 ```
$ cd /opt/staytus/staytus
```

Install all Ruby dependencies.

 ```
$ sudo -u staytus bundle install --deployment --without development:test
```

Update the database configuration.

 ```

$ sudo -u staytus cp config/database.example.yml config/database.yml
$ sudo -u staytus nano -w config/database.yml

```

Compile styleheets &amp; javascript files.

 ```
$ sudo -u staytus bundle exec rake staytus:build
```

Run setup tool.

 ```
$ sudo -u staytus bundle exec rake staytus:install
```

Run staytus by using below command.

 ```
$ sudo -u staytus procodile start --dev
```
