---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install SprintApp pms on Ubuntu

Install and configure the necessary dependencies packages. SprintApp project management software is easy to setup and get started. To get started with SprintApp on Heroku quickly, see our Deploying to Heroku Guide https://github.com/macfanatic/SprintApp/wiki/Deploying-to-Heroku.

Clone the repo to your computer or server

 ```
<pre class="command">```
git clone git://github.com/macfanatic/SprintApp.git sprint_app
cd sprint_app
```
```

Configure your database for use with the Rails app

 ```
<pre class="command">```
cp config/database.yml.sample config/database.yml
```
```

Run bundler

 ```
<pre class="command">```
bundle install --without production
```
```

Create and seed the database with default data and a user account

 ```
<pre class="command">```
bundle exec rake db:setup
```
```

Kick up a server with foreman running at localhost:5000

 ```
<pre class="command">```
bundle exec foreman start
```
```

Follow the configuration wizard steps and you have your OpenProject website ready to use. Login using default username: <span id="cloak9acd21a2df6105ca40d7f0711fec9ffb">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak9acd21a2df6105ca40d7f0711fec9ffb').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy9acd21a2df6105ca40d7f0711fec9ffb='&#97;dm&#105;n'+'&#64;';addy9acd21a2df6105ca40d7f0711fec9ffb=addy9acd21a2df6105ca40d7f0711fec9ffb+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text9acd21a2df6105ca40d7f0711fec9ffb='&#97;dm&#105;n'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak9acd21a2df6105ca40d7f0711fec9ffb').innerHTML+='<a '+path+'\''+prefix+':'+addy9acd21a2df6105ca40d7f0711fec9ffb+'\'>'+addy_text9acd21a2df6105ca40d7f0711fec9ffb+'<\/a>';</script> and password: password

There are a few ways you can customize SprintApp for your needs.

 ```
<pre class="command">```
Configure Carrierwave for Amazon S3
Edit the from address for Devise in the existing initializer
Edit the SMTP settings for outgoing mail, needed to email notifications of ticket updates for the production environment.
```
```

Congratulations! You have successfully installed SprintApp free project management tool. Enjoy!

<div class="col-lg-12"><a class="anchor" id="explore" name="explore"></a>Explore
-------

In this article we discussed about SprintApp open source project management and time tracking software. To learn about other open source project management softwares, please visit following page:

- [Best Open Source Project Management Tools](https://products.containerize.com/project-management)
 
 </div>