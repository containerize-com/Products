---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

### Install Edurge on Ubuntu

Edurge software is easy to setup and is one of the top 5 online learning platforms. To get started with Edurge free courses online Udemy clone on Ubuntu quickly, configure and setup Rails development environment with the necessary dependencies packages. First clone the Edurge repository in ~/edurge folder:

    git clone https://github.com/yshmarov/edurge

Switch to your Edurge folder and install the needed gems.

    cd ~/edurge
    bundle install

Now that you have successfully configured database connection, run the command to setup and migrate database:

    rails db:drop db:create db:migrate

Now, populate database with sample data:

    rails db:drop db:create db:migrate db:seed

Start rails server available only on localhost in development environment

    bundle exec rails server

You should now be able to connect to Edurge application on http://localhost:3000 - try it out. If you don't want any user to be able to create own courses, you should comment the field in user.rb to be like this

    self.add_role(:teacher)
    #self.add_role(:teacher)
    

Congratulations! You have successfully installed Edurge marketplace. Enjoy!