---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install SprintApp pms on Ubuntu

Install and configure the necessary dependencies packages. SprintApp project management software is easy to setup and get started. To get started with SprintApp on Heroku quickly, see our Deploying to Heroku Guide https://github.com/macfanatic/SprintApp/wiki/Deploying-to-Heroku.

Clone the repo to your computer or server

    git clone git://github.com/macfanatic/SprintApp.git sprint_app
    cd sprint_app

Configure your database for use with the Rails app

    cp config/database.yml.sample config/database.yml

Run bundler

    bundle install --without production

Create and seed the database with default data and a user account

    bundle exec rake db:setup

Kick up a server with foreman running at localhost:5000

    bundle exec foreman start

Follow the configuration wizard steps and you have your OpenProject website ready to use. Login using default username: admin@example.com and password: password

There are a few ways you can customize SprintApp for your needs.

    Configure Carrierwave for Amazon S3
    Edit the from address for Devise in the existing initializer
    Edit the SMTP settings for outgoing mail, needed to email notifications of ticket updates for the production environment.

Congratulations! You have successfully installed SprintApp free project management tool. Enjoy!
