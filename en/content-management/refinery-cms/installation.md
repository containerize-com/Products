---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Refinery CMS on Ubuntu

There are two popular ways to install Refinery: RubyGems and Rails Application Templates. We will discuss both and how you can get up and running with either.

**1. RubyGems:** The easiest way to install Refinery is to take advantage of RubyGems. This step may take some time to load as it needs to download and install all the ruby gems Refinery depends on

 ```
 gem install refinerycms 
```

**2. Rails Application Templates:** These application templates are another very easy way to install Refinery, and allow for a great deal of control of your installation. You can create a new Refinery application by typing

 ```
rails new rickrockstar -m https://www.refinerycms.com/t/4.0.0
cd rickrockstar 
```

Open up that folder and explore its contents. You'll notice what you have is a very standard Rails application. One of the traditional places to start with a new project is by getting some text up on screen quickly. To do this, you need to get your Refinery application server running. Once you've registered your first user you'll see Refinery's admin.

You'll need to set your Site Name. To do this, you'll have to edit config/initializers/refinery/core.rb. Look for the line that begins:

 ```
 config.site_name = "Company Name"  
```

Now you're setup, click around the various tabs in the back-end and become familiar with what comes out of the box.

Congratulation! You have successfully installed Refinery CMS and now build, customize and scale your CMS with no limits.