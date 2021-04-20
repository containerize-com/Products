---
title: Installation Guide
onpagelink: installation
weight: 3

---

**Installation Instructions to setup the production environment**
-----------------------------------------------------------------

### Installation on Ubuntu

Install and configure the necessary dependencies packages.

1\. Get the code. Clone this git repository and check out the latest release:

 ```
git clone git://github.com/sharetribe/sharetribe.git
cd sharetribe
git checkout latest
```

2\. Install the required gems by running the following command in the project root directory:

 ```
 bundle install 
```

3\. Install node modules:

 ```
 npm install 
```

4\. Create a database.yml file by copying the example database configuration:

 ```
 cp config/database.example.yml config/database.yml 
```

5\. Add your database configuration details to config/database.yml. You will probably only need to fill in the password for the database(s).

6\. Set secret\_key\_base and generate secret key

 ```
```
 rake secret 
``` Add the following lines to config/config.yml: production: secret_key_base: # add here the generated key
```

Note: You can also set the secret\_key\_base environment variable, if you don't want to store the secret key in a file

7\. Create the database:

 ```
 RAILS_ENV=production bundle exec rake db:create 
```

8\. Initialize your database:

 ```
 RAILS_ENV=production bundle exec rake db:structure:load 
```

9\. Run Sphinx index:

 ```
 RAILS_ENV=production bundle exec rake ts:index 
```

10\. Start the Sphinx daemon:

 ```
 RAILS_ENV=production bundle exec rake ts:start 
```

11\. Precompile the assets:

 ```
 RAILS_ENV=production NODE_ENV=production bundle exec rake assets:precompile 
```

12\. Invoke the delayed job worker:

 ```
 RAILS_ENV=production bundle exec rake jobs:work 
```

13\. In a new console, open the project root folder and start the server:

 ```
 bundle exec rails server -e production 
```

The built-in WEBrick server (which was started in the last step above) should not be used in production due to performance reasons. A dedicated HTTP server such as unicorn is recommended.

It is not recommended to serve static assets from a Rails server in production. Instead, you should use a CDN (Content Delivery Network) service, such as Amazon CloudFront. To serve the assets from the CDN service, you need to change the asset\_host configuration in the the config/config.yml file to point your CDN distribution.

You need to configure a couple scheduled tasks in order to properly run your marketplace in production. See the Scheduled tasks documentation.

For production use we recommend you to upgrade only when new version is released and not to follow the master branch.

**Setting your domain:**
------------------------

In your database, change the value of the domain column in the communities table to match the hostname of your domain. For example, if the URL for your marketplace is http://mymarketplace.myhosting.com, then the domain is mymarketplace.myhosting.com.

Change the value of the use\_domain column to true (or 1) in the communities table.

If you wish to enable HTTP Strict Transport Security (recommended), set also the hsts\_max\_age column in communities table to a non-zero number of seconds. For instance 31536000 (1 year).

You can read about ShareTribe’s features in more detail on the platform’s site, but the idea here is that ShareTribe has everything our clients typically ask for.

Congrats. You have successfully installed ShareTribe peer-to-peer marketplace.