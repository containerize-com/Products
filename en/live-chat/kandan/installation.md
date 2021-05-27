---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install Kandan on Ubuntu

<span style="font-size: 12.16px;">If you're looking to install Kandan chat application on a private stand alone server or to develop locally, then here is the path you must follow.</span>

 ```
git clone https://github.com/kandanapp/kandan.git 
cd kandan
```

<span style="font-size: 12.16px;">Lots of the gems require other libraries:</span>

 ```
sudo apt-get install ruby1.9.1-dev ruby-bundler libxslt-dev libxml2-dev libpq-dev libsqlite3-dev
```

<span style="font-size: 12.16px;">Some gems build native extensions:</span>

 ```
sudo apt-get install gcc g++ make
```

<span style="font-size: 12.16px;">For development-mode</span>

 ```
sudo apt-get install nodejs # (execjs needs an execution environment)
gem install execjs # (Could possibly be added to the gemfile in the assets group)
```

<span style="font-size: 12.16px;">Install the required gems:</span>

 ```
bundle install
```

<span style="font-size: 12.16px;">You can use the default database.yml to get started in development. For production you'll need to edit config/database.yml to add something like this:</span>

 ```

production:
  adapter: postgresql
  host: localhost
  database: kandan_production
  pool: 5
  timeout: 5000
  # You might need these depending on your Postgres auth setup.
  username: kandan 
  password: something

```

<span style="font-size: 12.16px;">Now, bootstrap the install. you can omit the db:create step if you have already created the DB referenced above:</span>

 ```
bundle exec rake db:create db:migrate kandan:bootstrap
```

<span style="font-size: 12.16px;">If you plan to serve the app directly from Thin (rather than through a proxy), you will need to configure Rails to serve assets in the production environment. In config/environments/production.rb:</span>

 ```
config.serve_static_assets = true
```

<span style="font-size: 12.16px;"> Start the rails server</span>

 ```
bundle exec thin start
```

<span style="font-size: 12.16px;">Your app should be up and running now. The default admin user is Admin with password kandanappadmin, or you can sign up as another user. </span>

<span style="font-size: 12.16px;">Congratulations! You have successfully installed Kandan open source chat application. Enjoy!</span>

<div class="asposeptyltd containerize"> </div><div class="col-lg-12">Explore
-------

In this article we have discussed Kandan chat application that allows you to manage several conversations simultaneously. To learn about other open source live chat software, please visit page:

- [Best Open Source Live Chat Applications](https://products.containerize.com/live-chat)
 
 </div>