---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

Clone the latest Helpy repository into document root folder:

 ```
<pre class="command">```
git clone https://github.com/helpyio/helpy.git
```
```

Next, install dependencies:

 ```
<pre class="command">```
bundle install
```
```

Now set up the database and secrets files:

 ```
<pre class="command">```
cp config/database.do.yml config/database.yml
rake secret
# copy the key to
nano config/secrets.yml
nano config/database.yml
touch /home/deploy/helpy/log/production.log
chmod 0664 /home/deploy/helpy/log/production.log

```
```

Unpack the Helpy assets and setup your database:

 ```
<pre class="command">```
RAILS_ENV=production rake assets:precompile
RAILS_ENV=production rake db:setup

```
```

Now start up passenger/nginx and your site should be live!