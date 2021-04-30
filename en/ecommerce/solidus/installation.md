---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Solidus on Linux (Debian-based)

Making sure you have Imagemagick installed, which is required for Paperclip.To add solidus, begin with a Rails 5/6 application and a database configured and created. Clone the Git repo and install the gem dependencies.

    git clone git://github.com/solidusio/solidus.git
    cd solidus
    bin/setup

For Solidus v2.11 and above, Add the following to your Gemfile.

    gem 'solidus'

Run the bundle command to install.

    bundle install

After installing gems, you'll have to run the generator to create necessary configuration files and migrations.

    bin/rails g solidus:install

Start the Rails server with the command to access solidus store

    bin/rails s

The solidus\_frontend storefront will be accessible at http://localhost:3000/ and the admin can be found at http://localhost:3000/admin/.

You may notice that your Solidus store runs slowly in development mode. This can be because in development each CSS and JavaScript is loaded as a separate include. This can be disabled by adding the following to config/environments/development.rb.

    Rails.application.configure do
      config.assets.debug = false
    end

The default user and password are [admin@example.com](mailto:admin@example.com) and test123, respectively. There are also options and rake tasks provided by solidus\_auth\_devise.

Congratulations! You have successfully installed Solidus store and now customize any of the built-in features to your heart's desire.