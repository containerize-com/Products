---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Spree Commerce on Ubuntu

Spree Commerce best open source ecommerce version 4.1.0 is now available and here are instructions to setup a new E-Commerce project. Add Spree gems to your Gemfile

 ```
gem 'spree', '~> 4.1'
gem 'spree_auth_devise', '~> 4.2'
gem 'spree_gateway', '~> 3.9' 
```

Older rails versions are also supported: Rails 5.1, Rails 5.0, Rails 4.2. To install gems run below command:

 ```
 bundle install 
```

Note: if you run into Bundler could not find compatible versions for gem "sprockets": error message, please run.

 ```
 bundle update 
```

Use the install generators to set up Spree.

 ```
bundle exec rails g spree:install --user_class=Spree::User
bundle exec rails g spree:auth:install
bundle exec rails g spree_gateway:install 
```

To use Spree in API-only mode you need to replace spree with spree\_api in your project Gemfile. This will skip Storefront and Admin Panel. If you would want to include the Admin Panel please add spree\_backend to your Gemfile. Feel free to explore some of the Admin Panel features that Spree has to offer and to verify that your installation is working properly.

Congrats. You have successfully installed spree store and now build, customize and scale your store with no limits.