---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Sidekiq on Ubuntu**

Sidekiq simple, easy to setup and open source task scheduler. To configure and setup Sidekiq recurring jobs with Rails environment, install the necessary dependencies packages. Add sidekiq gem to run job in background linux to your Gemfile or run below command in project directory:

    gem install sidekiq

Add a worker in app or workers to process linux background jobs asynchronously:

    rails generate sidekiq:worker hard

Create the database and run migrations:

    HardWorker.perform_async('bob', 5)

Start sidekiq unique jobs from the root of your Rails application so the jobs will be processed:

    bundle exec sidekiq

Congratulations! You have successfully installed sidekiq open source job scheduler with ui software. Enjoy!