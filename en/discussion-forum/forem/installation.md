---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Forem on Ubuntu

There are many different ways to install Forem for how to build a community but here we will discuss installation steps for Ubuntu. Forem community building project is easy to setup and get started. To get started with Forem for how to create a community quickly, configure and setup Rails development environment with the necessary dependencies packages.

    sudo npm install -g yarn
    sudo apt-get install libpq-dev
    sudo apt-get install g++
    sudo nvm install node

Now first clone the Forem repository in ~/forem repository:

    git clone https://github.com/forem/forem.git forem
    cd forem

Now, run the bundler in project directory:

    gem install bundler

Set up your environment variables and secrets. Create .env by copying from the provided template

    cp .env_sample .env

The following environment variables can be set:

    export CLOUDINARY_API_KEY="SOME_REAL_SECURE_KEY_HERE"
    export CLOUDINARY_API_SECRET="ANOTHER_REAL_SECURE_KEY_HERE"
    export CLOUDINARY_CLOUD_NAME="A_CLOUDINARY_NAME"

Setup the database and run migrations:
    rake db:create db:migrate

Congratulations! You have successfully installed Forem online community management software. Enjoy!