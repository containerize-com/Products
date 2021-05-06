---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install OpenSourceBilling on Ubuntu(LTS)

Deploy OpenSourceBilling in a way that’s right for your business. MySql is an open-source relational database management system. Run the following command to install database:

 ```
sudo apt-get install mysql-server mysql-client libmysqlclient-dev
```

Git is version control system we used for OSB. Run the following command to install git.

 ```
sudo apt-get install git 
```

Run the following command to install ruby dependencies:

 ```
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libncurses5-dev automake libtool bison libffi-dev imagemagick libmagickcore-dev libmagickwand-dev libicu-dev 
```

You may need access to dependent pecl libraries, most which can be found by

 ```
sudo add-apt-repository ppa:ondrej/php 
```

Run the following commands to install stable version.

 ```
curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.7.1
rvm use 2.7.1 --default 
```

Bundler is a tool that allows you to install multiple gem versions, run this command to install bundler:

 ```
gem install bundler
```

To clone project code from GitHub, give your GitHub account credential for authentication while cloning project.

 ```
git clone https://github.com/vteams/open-source-billing
cd open-source-billing
bundle install
yarn install

```

Copy config/config.yml.copy to config/config.yml to set your configurations. Edit config/config.yml with your own paypal settings:

 ```
paypal:
  signature: YOUR_PAYPAL_SIGNATURE
  business: YOUR_PAYPAL_BUSINESS

```

Edit config/config.yml with your own application settings:

 ```
app_host: APP_HOST_HERE # e.g. osb.mydomain.com
app_protocol: http
```

Using following command in terminal to get path of wkhtmltopdf library path that is already installed on system and then edit config/config.yml with your own application wkhtmltopdf path.

 ```
wkhtmltopdf_path: YOUR_WKHTMLTOPDF_PATH
```

To make smtp\_settings, go to settings, open a company edit form by clicking on a company and provide your smtp details in Mail Config section.

Edit config/config.yml with your own QuickBooksApp's oauth\_consumer\_key and oauth\_consumer\_secret.

 ```
quickbooks:
   # QuickBooksApp's account key and secret
   consumer_key: YOUR_QUICKBOOKS_APP_CLIENT_ID
   consumer_secret: YOUR_QUICKBOOKS_APP_CLIENT_SECRET
```

Run following command on terminal to run application

 ```
rake secret
encryption_key: ENTER-YOUR-ENCRYPTED-KEY-HERE
rails db:create
rails db:migrate
rails db:seed

```

You need to start delayed\_job for email delivery and other background tasks required for properly functionality of OSB by using following command

 ```
RAILS_ENV=production  bin/delayed_job start
```

Once you successfully configured OSB, you can use the below credentials to login.

 ```
Email: <span id="cloak1a36824b07bcee77581f96f7957d6335">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak1a36824b07bcee77581f96f7957d6335').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy1a36824b07bcee77581f96f7957d6335='&#97;dm&#105;n'+'&#64;';addy1a36824b07bcee77581f96f7957d6335=addy1a36824b07bcee77581f96f7957d6335+'&#111;p&#101;ns&#111;&#117;rc&#101;b&#105;ll&#105;ng'+'&#46;'+'&#111;rg';var addy_text1a36824b07bcee77581f96f7957d6335='&#97;dm&#105;n'+'&#64;'+'&#111;p&#101;ns&#111;&#117;rc&#101;b&#105;ll&#105;ng'+'&#46;'+'&#111;rg';document.getElementById('cloak1a36824b07bcee77581f96f7957d6335').innerHTML+='<a '+path+'\''+prefix+':'+addy1a36824b07bcee77581f96f7957d6335+'\'>'+addy_text1a36824b07bcee77581f96f7957d6335+'<\/a>';</script>
password: opensourcebilling
```

You should configure Apache, Nginx or any other web/application server of your choice to execute OSB in production mode. When a customer receive invoice/estimate through email, he will also receive a login link to see all of his invoices. By visiting that url he can login to his account or can create his account if he don't have one.

Congratulations! You have successfully installed OpenSourceBilling on your system.