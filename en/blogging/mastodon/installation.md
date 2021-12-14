---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Mastodon On Ubuntu**

Mastodon open source social media platform is based on ActivityPub which is easy to get started. The best way of operating with Mastodon in a local development environment is installing all the system dependencies in your local environment instead of using Docker or Vagrant tools. Install standard set of dependencies for Rails applications like Ruby, Node.js, PostgreSQL and Redis etc. You can download the latest stable release of Mastodon microblogging tool by running commands in terminal:

    git clone https://github.com/tootsuite/mastodon.git mastodon
    cd mastodon
    git checkout $(git tag -l | grep -v 'rc[0-9]*$' | sort -V | tail -n 1)

Next, install Ruby and JavaScript the lastest dependencies by running the bundler in project directory:

    bundle install

Now update the database.yml and run the interactive setup wizard with following command:

    bundle exec rake mastodon:setup

There are multiple processes that need to be run for the full set of functionality of Mastodon. You can install and start Foreman to run all of processes with:

    gem install foreman --no-document
    foreman start

In the Mastodon directory, this will start processes defined in Procfile.dev, A Rails server, a Webpack server, a streaming API server and Sidekiq schedular. That's it.

Congratulatiopns! you have successfully installed Mastodon most popular microblogging site on your Ubuntu system. Enjoy!