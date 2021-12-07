---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Chaskiq on Ubuntu**

Chaskiq marketing management software is easy to setup and get started. To get started with Chaskiq on Ubuntu quickly, configure and setup Rails development environment with the necessary dependencies packages by running this script in terminal:

    bash <(wget -qO- https://raw.githubusercontent.com/techAPJ/install-rails/master/linux)

First clone the Chaskiq repository in ~/chaskiq folder:

    git clone https://github.com/chaskiq/chaskiq.git ~/chaskiq

Create role with the same name as your ubuntu system username:

    sudo -u postgres createuser -s "$USER"

Switch to your Chaskiq folder and Install the needed gems

    cd ~/chaskiq
    bundle install

Now that you have successfully configured database connection, run these commands:

    bundle exec rake db:create 
    bundle exec rake db:schema:load
    bundle exec rake db:seed
    RAILS_ENV=test bundle exec rake db:test:clone

Now, try running the specs tests:

    bundle exec rake rspec

Start rails server available only on localhost

    bundle exec rails server

You should now be able to connect to chaskiq business management app on http://localhost:3000 - try it out. To create a new admin, run the following command:

    RAILS_ENV=development bundle exec rake admin_generator

Follow the prompts, and a new admin account will be created. If you want to set up a Chaskiq marketing business for production use, see our [Chaskiq Installation Guide](https://dev.chaskiq.io/en/collections/production-configuration).

Congratulations! You have successfully installed Chaskiq business marketing tool. Enjoy!