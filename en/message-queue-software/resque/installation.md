---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Resque on Ubuntu**

Resque open source batch scheduler is simple and easy to get started software. First install the necessary dependencies packages. If you use Debian based distro such as Ubuntu, run below commands in terminal to install and automatically start Redis with Resque open source scheduler on boot:

    sudo apt install redis
    sudo systemctl enable redis

Next, install resque gem in your project directory or add resque gem to your Gemfile:

    gem 'resque'

Now, install it with Bundler:

    bundle install

In your Rakefile, or some other file in lib/tasks (ex: lib/tasks/resque.rake), load the resque rake tasks:

    require 'resque'
    require 'resque/tasks'

Include below line if you want your workers to have access to your application:

    require 'your/app'

Resque batch job scheduler workers are rake tasks that run forever. You can starting a worker:

    QUEUE=* rake resque:work

You can start multiple workers with:

    COUNT=2 QUEUE=* rake resque:workers

If you want your workers to work off of every queue, including new queues created on the fly, you can use:

    QUEUE=* rake resque:work

If you've installed Resque as a gem running the front end then standalone is easy to run:

    resque-web

Press ctrl-c to kill background process all workers. Resque workers support basic logging to STDOUT. You can control the logging threshold in config/initializers/resque.rb

    Resque.logger.level = Logger::DEBUG

Now start your application:

    rails server

Congratulations! You have successfully installed Resque open source batch scheduler on linux cloud server. Enjoy!
