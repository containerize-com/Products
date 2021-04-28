---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Edurge on Ubuntu

Edurge software is easy to setup and is one of the top 5 online learning platforms. To get started with Edurge free courses online Udemy clone on Ubuntu quickly, configure and setup Rails development environment with the necessary dependencies packages. First clone the Edurge repository in ~/edurge folder:

 ```
<pre class="command">```
git clone https://github.com/yshmarov/edurge
```
```

Switch to your Edurge folder and install the needed gems.

 ```
<pre class="command">```
cd ~/edurge
bundle install
```
```

Now that you have successfully configured database connection, run the command to setup and migrate database:

 ```
<pre class="command">```
rails db:drop db:create db:migrate
```
```

Now, populate database with sample data:

 ```
<pre class="command">```
rails db:drop db:create db:migrate db:seed
```
```

Start rails server available only on localhost in development environment

 ```
<pre class="command">```
bundle exec rails server
```
```

You should now be able to connect to Edurge application on http://localhost:3000 - try it out. If you don't want any user to be able to create own courses, you should comment the field in user.rb to be like this

 ```
<pre class="command">```
self.add_role(:teacher)
#self.add_role(:teacher)

```
```

Congratulations! You have successfully installed Edurge marketplace. Enjoy!

<div class="col-lg-12"><a class="anchor" id="explore" name="explore"></a>Explore
-------

In this article we discussed about Edurge courses online free open source marketplace software. To learn about other open source marketplace softwares, please visit following page:

- [Best Open Source Marketplace Softwares](https://products.containerize.com/marketplace)
 
 </div>