---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Sidekiq on Ubuntu

Sidekiq simple, easy to setup and get started software. To configure and setup Sidekiq with Rails environment, install the necessary dependencies packages. Add sidekiq gem to your Gemfile or run below command in project directory:

    gem install sidekiq

Add a worker in app or workers to process jobs asynchronously:

    rails generate sidekiq:worker hard

Create the database and run migrations:

    HardWorker.perform_async('bob', 5)

Start sidekiq from the root of your Rails application so the jobs will be processed:

    bundle exec sidekiq

Congratulations! You have successfully installed sidekiq software. Enjoy!

Explore
-------

In this article we discussed about Sidekiq background processing tool. To learn about other open source background job processing systems, please visit following page:

*   [Top Open Source Message Queue (MQ) Softwares List](https://products.containerize.com/message-queue-software/)