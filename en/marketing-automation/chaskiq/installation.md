---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Chaskiq on Ubuntu

Chaskiq marketing management software is easy to setup and get started. To get started with Chaskiq on Ubuntu quickly, configure and setup Rails development environment with the necessary dependencies packages by running this script in terminal:

 ```
<pre class="command">```
bash <(wget -qO- https://raw.githubusercontent.com/techAPJ/install-rails/master/linux)
```
```

First clone the Chaskiq repository in ~/chaskiq folder:

 ```
<pre class="command">```
git clone https://github.com/chaskiq/chaskiq.git ~/chaskiq
```
```

Create role with the same name as your ubuntu system username:

 ```
<pre class="command">```
sudo -u postgres createuser -s "$USER"
```
```

Switch to your Chaskiq folder and Install the needed gems

 ```
<pre class="command">```
cd ~/chaskiq
bundle install
```
```

Now that you have successfully configured database connection, run these commands:

 ```
<pre class="command">```
bundle exec rake db:create 
bundle exec rake db:schema:load
bundle exec rake db:seed
RAILS_ENV=test bundle exec rake db:test:clone
```
```

Now, try running the specs tests:

 ```
<pre class="command">```
bundle exec rake rspec
```
```

Start rails server available only on localhost

 ```
<pre class="command">```
bundle exec rails server
```
```

You should now be able to connect to chaskiq business management app on http://localhost:3000 - try it out. To create a new admin, run the following command:

 ```
<pre class="command">```
RAILS_ENV=development bundle exec rake admin_generator
```
```

Follow the prompts, and a new admin account will be created. If you want to set up a Chaskiq marketing business for production use, see our [Chaskiq Installation Guide](https://dev.chaskiq.io/en/collections/production-configuration).

Congratulations! You have successfully installed Chaskiq business marketing tool. Enjoy!

<div class="col-lg-12"><a class="anchor" id="explore" name="explore"></a>Explore
-------

In this article we discussed about Chaskiq open source software. To learn about other open source free online business marketing management softwares, please visit following page:

- [Best Open Source Business Marketing Management Softwares](https://products.containerize.com/marketing-automation)
 
 </div>