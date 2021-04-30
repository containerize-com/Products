---
title: Installation Guide
onpagelink: installation
weight: 3

---
Installation Instructions
-------------------------

### Install Loomio on Ubuntu

First make sure you have installed all the dependencies. Now please follow below step by step guide to set up development environment and run your own Loomio installations: If you are familiar with the process of running rails, we recommend you visit https://github.com/loomio/loomio then click 'Fork' to create your own loomio repository to work from. Then clone that repo to your local computer:

    git clone git@github.com:YOURUSERNAME/loomio.git 
    cd loomio

Install ruby and node dependencies then check out loomio repo:

    bundle install
    cd vue; npm install && cd ..

Create a database.yml file

    cp config/database.example.yml config/database.yml

Setup the Loomio database and schema

    bundle install
    rake db:setup

To run the Loomio server and automatically rebuilds it when you make changes

    USE_VUE=1 rails s
    cd vue
    npm run serve

Run the rails development server

    bundle exec rails s

Then start lineman from the loomio/lineman folder

    lineman run

You can view Loomio in your browser by visiting http://localhost:8080. To view Loomio’s features and changes to your source code, visit any of the dev routes listed at http://localhost:8080/dev/.

If you are deploying Loomio on a public server, we recommend you use our Loomio [Deploy repo](https://github.com/loomio/loomio-deploy)

Congratulations! You have successfully installed Loomio free decision making software online. Enjoy!

Explore
-------

In this article we have discussed about Loomio decision making process in management. To learn about other open source decision making software, please visit following page:

*   [Best Open Source Decision Making Software](https://products.containerize.com/discussion-forum)