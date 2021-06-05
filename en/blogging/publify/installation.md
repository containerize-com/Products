---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Publify On Ubuntu

Publify web publishing software is simple and easy to get started software. Install and configure ruby on rails, database, build tools and ruby dependencies on ubuntu. Here we will setup publify development environment. You can download the latest version of the Publify from Git repository using git clone command on your local machine:

    git clone https://github.com/publify/publify.git
    cd ~/publify

Next, rename the sample database.yml file as database.yml with the following command:

    cp ~/publify/config/database.yml.mysql ~/publify/config/database.yml

Next, open database.yml file and make some changes inside it to add your database name, login and password:

    sudo nano ~/publify/config/database.yml

Add the following lines in database.yml:

    development:
      login: &login
      adapter: mysql2
      host: localhost
      username: publify
      password: password

Run bundler to install gems in project directory:

    bundle install

Next, prepare the database and compile the assets wit the following command:

    rails db:setup 
    rails db:migrate
    rails db:seed
    rails assets:precompile

Once everything is configured then run rails server using following:

    rails server

Launch your web browser, type the URL http://127.0.0.1:3000 and complete required steps to finish the Publify installation. That's it.

Congratulatiopns! you have successfully installed Publify on your Ubuntu system. Enjoy!
