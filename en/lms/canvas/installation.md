---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Canvas on Ubuntu 18.04 LTS**

#### Install Curl

Run the following command to install curl.

 ```
sudo apt-get install curl 
```

#### Install Git

Run the command below to install Git.

 ```
sudo apt-get install git 
```

#### Install Ruby

Add Node.js, Yarn repositories and their keys to your system by runnig the below commands.

 ```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

Update packages and install core packages with the following commands.

 ```
sudo apt-get update
sudo apt-get install nodejs zlib1g-dev build-essential libpq-dev libssl-dev redis-server libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev zlib1g-dev libxml2-dev libsqlite3-dev libpq-dev libxmlsec1-dev make g++ libxslt1-dev libcurl4-openssl-dev libffi-dev 
```

Install Ruby with your local profile settings using rbenv.

 ```
cd ~/
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL 
```

Now, run the following commands to install Ruby.

 ```
rbenv install 2.5.3
rbenv global 2.5.3
```

Run the below commands to install bundler.

 ```
gem install bundler -v 1.13.6
rbenv rehash
```

#### Install PostgreSQL

Run commnad to install PostreSQL database server.

 ```
sudo apt-get install postgresql
```

Run the commands below to create a database user called **canvas**.

 ```
sudo -u postgres createuser canvas --no-createdb --no-superuser --no-createrole --pwprompt 
```

Run the following command to create a new database called "canvasdb" and make canvas owner.

 ```
sudo -u postgres createdb canvas_production --owner=canvas
```

Once done with the PostreSQL installation, set system username as a postgres superuser.

 ```
sudo -u postgres createuser $USER
sudo -u postgres psql -c "alter user $USER with superuser" postgres
```

#### Install Yarn

Next, run the commands below install Rails, add Node.js repository and install Node.js package.

 ```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt-get update && sudo apt-get install yarn=1.10.1-1
```

Update Rubygems with the following command.

 ```
gem update --system
```

#### Install Canvas LMS

Navigate to home directory and clone canvas repository.

 ```
cd ~/
git clone https://github.com/instructure/canvas-lms.git
```

Change directory and checkout stable branch.

 ```
cd canvas-lms
git checkout stable
```

Run the commands below configure Canvas environment.

 ```
for config in amazon_s3 database delayed_jobs domain file_store outgoing_mail security external_migration; do cp config/$config.yml.example config/$config.yml; done

```

Create Canvas dynamic settings file and database configuration file.

 ```
cp config/dynamic_settings.yml.example config/dynamic_settings.yml
cp config/database.yml.example config/database.yml
```

Open file config/database.yml and set Canvas database credentials.

 ```
sudo nano config/database.yml
```

Edit the production configuration lines and save the file.

 ```
production:
   adapter: postgresql
   encoding: utf8
   database: canvasdb
   host: localhost
   username: canvas
   password: passwore_here
   timeout: 5000
```

Download all Canvas dependencies by running these commands.

 ```
bundle install
yarn install --pure-lockfile && yarn install --pure-lockfile
sudo npm install -g coffee-script@1.6.2
```

Finally, run the commands below to setup Canvas.

 ```
bundle exec rails db:initial_setup
bundle exec rails canvas:compile_assets
bundle exec rails server
```

Now, open browser and type http://localhost:3000 to access the Canvas.
