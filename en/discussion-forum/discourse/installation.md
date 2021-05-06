---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

### Installation using Github

Clone the Discourse repository

    git clone https://github.com/discourse/discourse.git ~/discourse

Create role with the same name as your ubuntu system username:

    sudo -u postgres createuser -s "$USER"

Switch to your Discourse folder and install the needed gems

    cd ~/discourse 
    source ~/.bashrc 
    bundle install

Now that you have successfully configured database connection, run these commands:

    bundle exec rake db:create 
    bundle exec rake db:migrate
    RAILS_ENV=test bundle exec rake db:create db:migrate

Now, try running the specs:

    bundle exec rake autospec

Start rails server:

    bundle exec rails server

### Installation using Docker

After you have logged in as the root user, we can begin the docker install by entering the following commands. You should use the root user throughout the rest of the setup and bootstrapping process.

     sudo -s  

     git clone https://github.com/discourse/discourse_docker.git /var/discourse  

Now, cd into the Discourse folder.

     cd /var/discourse  

Next, you will run the Discourse setup command.

     ./discourse-setup 

Next, you will be asked a series of questions that are required to move forward with the installation.

    Hostname for your Discourse? [forum.example.com]:
    Email address for admin account(s)? [me@example.com]:
    SMTP server address? [smtp.example.com]:
    SMTP port? [587]:
    SMTP user name? [user@example.com]:
    SMTP password? [pa$$word]:
    Let's Encrypt account email? (ENTER to skip) [me@example.com]:

The Discourse setup will create an app.yml file and kick off the bootstrapping process, which can take anywhere from two to eight minutes. Once this portion completes, you can move on to the browser-based setup.

Congrats! You have successfully installed Discourse