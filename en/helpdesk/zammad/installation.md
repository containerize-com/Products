---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Zammad on Debian 7, 8 / Ubuntu 16.04 / Ubuntu 18.04 (with Nginx &amp; MySQL)

Prerequisites

 ```
apt-get update 
apt-get install curl git-core patch build-essential bison zlib1g-dev libssl-dev libxml2-dev libxml2-dev sqlite3 libsqlite3-dev autotools-dev libxslt1-dev libyaml-0-2 autoconf automake libreadline6-dev libyaml-dev libtool libgmp-dev libgdbm-dev libncurses5-dev pkg-config libffi-dev libmysqlclient-dev mysql-server nginx gawk libimlib2-dev
```

Add User

 ```
useradd zammad -m -d /opt/zammad -s /bin/bash 
echo "export RAILS_ENV=production" >> /opt/zammad/.bashrc 
```

Create MySQL user zammad

 ```
 mysql --defaults-extra-file=/etc/mysql/debian.cnf -e "CREATE USER 'zammad'@'localhost' IDENTIFIED BY 'Your_Pass_Word'; GRANT ALL PRIVILEGES ON zammad_prod.* TO 'zammad'@'localhost'; FLUSH PRIVILEGES;" 
```

Get Zammad

 ```
su - zammad
curl -O https://ftp.zammad.com/zammad-latest.tar.gz
tar -xzf zammad-latest.tar.gz
rm zammad-latest.tar.gz 
```

Install environment

 ```
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
curl -L https://get.rvm.io | bash -s stable
source /opt/zammad/.rvm/scripts/rvm
echo "source /opt/zammad/.rvm/scripts/rvm" >> /opt/zammad/.bashrc
echo "rvm --default use 2.6.5" >> /opt/zammad/.bashrc
rvm install 2.6.5
gem install bundler
```

Install Zammad

 ```
bundle install --without test development postgres
cp config/database/database.yml config/database.yml

```

Insert mysql user, pass &amp; change adapter to mysql2 &amp; change database to zammad\_prod.

 ```
vi config/database.yml 
rake db:create 
rake db:migrate 
rake db:seed 
rake assets:precompile
```

Start Zammad

 ```
rails s -p 3000 &>> log/zammad.log &
script/websocket-server.rb start &>> log/zammad.log &
script/scheduler.rb start &>> log/zammad.log &
```

Create Nginx Config &amp; restart Nginx

 ```
exit
cp /opt/zammad/contrib/nginx/zammad.conf /etc/nginx/sites-available/zammad.conf
```

Change servername “localhost” to your domain if your’re not testing localy

 ```
vi /etc/nginx/sites-available/zammad.conf
ln -s /etc/nginx/sites-available/zammad.conf /etc/nginx/sites-enabled/zammad.conf
systemctl restart nginx
```

Go to http://localhost and you’ll see

- <span style="font-size: 12.16px;">“Welcome to Zammad!”, there you need to create your admin user and invite other agents.</span>
 
Congrats! You have successfully installed Zammad on NGINX