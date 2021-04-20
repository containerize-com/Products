---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

First make sure you have installed all the dependencies. Clone the latest Redmine repository into document root folder:

 ```
<pre class="command">```
git clone https://github.com/redmine/redmine

```
```

Create MySQL Database with following commands:

 ```
<pre class="command">```
CREATE DATABASE redmine CHARACTER SET utf8mb4;
CREATE USER 'redmine'@'localhost' IDENTIFIED BY 'my_password';
GRANT ALL PRIVILEGES ON redmine.* TO 'redmine'@'localhost';

```
```

Copy config/database.yml.example to config/database.yml and edit this file in order to configure your database settings for "production" environment. Example for a MySQL database (default port):

 ```
<pre class="command">```
production:
  adapter: mysql2
  database: redmine
  host: localhost
  username: redmine
  password: "my_password"

```
```

Install Bundler first if you use Ruby 2.5 or earlier:

 ```
<pre class="command">```
gem install bundler
```
```

Then you can install all the gems required by Redmine using the following command:

 ```
<pre class="command">```
bundle install --without development test
```
```

Generating a new secret token invalidates all existing sessions after restart.

 ```
<pre class="command">```
bundle exec rake generate_secret_token
```
```

Create the database structure, by running the following command under the application root directory:

 ```
<pre class="command">```
RAILS_ENV=production bundle exec rake db:migrate
```
```

Windows syntax:

 ```
<pre class="command">```
set RAILS_ENV=production
bundle exec rake db:migrate

```
```

Insert default configuration data in database, by running the following command:

 ```
<pre class="command">```
RAILS_ENV=production bundle exec rake redmine:load_default_data
```
```

Redmine will prompt you for the data set language that should be loaded; you can also define the REDMINE\_LANG environment variable before running the command to a value which will be automatically and silently picked up by the task. Unices:

 ```
<pre class="command">```
RAILS_ENV=production REDMINE_LANG=fr bundle exec rake redmine:load_default_data
```
```

Windows:

 ```
<pre class="command">```
set RAILS_ENV=production
set REDMINE_LANG=fr

```
```

 ```
<pre class="command">```
bundle exec rake redmine:load_default_data
```
```

The user account running the application must have write permission on the following subdirectories: files (storage of attachments) log (application log file production.log) tmp and tmp/pdf (create these ones if not present, used to generate PDF documents among other things) public/plugin\_assets (assets of plugins) E.g., assuming you run the application with a redmine user account:

 ```
<pre class="command">```
mkdir -p tmp tmp/pdf public/plugin_assets
sudo chown -R redmine:redmine files log tmp public/plugin_assets
sudo chmod -R 755 files log tmp public/plugin_assets

```
```

Note: If you have files in these directories (e.g. restore files from backup), make sure these files are not executable.

 ```
<pre class="command">```
sudo find files log tmp public/plugin_assets -type f -exec chmod -x {} +

```
```

Test the installation by running WEBrick web server:

 ```
<pre class="command">```
bundle exec rails server webrick -e production

```
```

Once WEBrick has started, point your browser to http://localhost:3000/. You should now see the application welcome page.