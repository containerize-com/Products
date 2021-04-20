---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install LocomotiveCMS on Linux (Debian-based)

Locomotive following instructions only work for 64 bit Debian-based Linux distributions such as Ubuntu, Mint etc.

Create a new Ruby on Rails application:

 ```
rails new locomotiveapp --skip-bundle --skip-active-record
cd locomotiveapp
```

Make sure you delete the robots.txt file from public/ otherwise any future sites' robots.txt setting won't be picked up. Add the Mongoid and Devise gems in your Gemfile.

 ```
gem 'devise', '~> 4.7.1'
gem 'mongoid', '~> 6.4.0'
```

Install them and run their setup tasks

 ```
bundle install
bundle exec rails generate mongoid:config
bundle exec rails generate devise:install
```

Update the Gemfile of the Rails application by adding the locomotivecms gem.

 ```
gem 'locomotivecms', '~> 4.0.1'
```

Run the Locomotive installation generator

 ```
bundle update
bundle exec rails generate locomotive:install
```

The installation adds the puma gem to the Rails application's Gemfile. An additional bundle install is required:

 ```
bundle install
```

Finally, run the Rails server

 ```
rails server
```

That’s it! Now, open your browser at http://localhost:3000/locomotive. You should see the Locomotive Sign in page. Click on "Do not have an account?" link at the bottom page and fill in the Sign up form in order to create your first account. Now you can push a site template by installing Wagon and deploying your site to the Engine.

Congratulations! You have successfully installed Locomotive CMS platform.