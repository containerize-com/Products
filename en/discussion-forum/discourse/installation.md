---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

Clone the Discourse repository

 ```
git clone https://github.com/discourse/discourse.git ~/discourse
```

Create role with the same name as your ubuntu system username:

 ```
sudo -u postgres createuser -s "$USER"
```

Switch to your Discourse folder and install the needed gems

 ```
cd ~/discourse 
source ~/.bashrc 
bundle install
```

Now that you have successfully configured database connection, run these commands:

 ```
bundle exec rake db:create 
bundle exec rake db:migrate
RAILS_ENV=test bundle exec rake db:create db:migrate
```

Now, try running the specs:

 ```
bundle exec rake autospec
```

Start rails server:

 ```
bundle exec rails server
```

### Installation using Docker

After you have logged in as the root user, we can begin the docker install by entering the following commands. You should use the root user throughout the rest of the setup and bootstrapping process.

 ```
 sudo -s  
```

 ```
 git clone https://github.com/discourse/discourse_docker.git /var/discourse  
```

Now, cd into the Discourse folder.

 ```
 cd /var/discourse  
```

Next, you will run the Discourse setup command.

 ```
 ./discourse-setup 
```

Next, you will be asked a series of questions that are required to move forward with the installation.

 ```
Hostname for your Discourse? [forum.example.com]:
Email address for admin account(s)? [<span id="cloakba793ccc3a96f94373caeefeb493517c">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloakba793ccc3a96f94373caeefeb493517c').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addyba793ccc3a96f94373caeefeb493517c='m&#101;'+'&#64;';addyba793ccc3a96f94373caeefeb493517c=addyba793ccc3a96f94373caeefeb493517c+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_textba793ccc3a96f94373caeefeb493517c='m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloakba793ccc3a96f94373caeefeb493517c').innerHTML+='<a '+path+'\''+prefix+':'+addyba793ccc3a96f94373caeefeb493517c+'\'>'+addy_textba793ccc3a96f94373caeefeb493517c+'<\/a>';</script>,<span id="cloak0e6bb9e1f4a5a13a657bb549fd7b598e">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak0e6bb9e1f4a5a13a657bb549fd7b598e').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy0e6bb9e1f4a5a13a657bb549fd7b598e='y&#111;&#117;'+'&#64;';addy0e6bb9e1f4a5a13a657bb549fd7b598e=addy0e6bb9e1f4a5a13a657bb549fd7b598e+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text0e6bb9e1f4a5a13a657bb549fd7b598e='y&#111;&#117;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak0e6bb9e1f4a5a13a657bb549fd7b598e').innerHTML+='<a '+path+'\''+prefix+':'+addy0e6bb9e1f4a5a13a657bb549fd7b598e+'\'>'+addy_text0e6bb9e1f4a5a13a657bb549fd7b598e+'<\/a>';</script>]:
SMTP server address? [smtp.example.com]:
SMTP port? [587]:
SMTP user name? [<span id="cloakce48818c47e6f537b7a3c0d9360a6d51">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloakce48818c47e6f537b7a3c0d9360a6d51').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addyce48818c47e6f537b7a3c0d9360a6d51='&#117;s&#101;r'+'&#64;';addyce48818c47e6f537b7a3c0d9360a6d51=addyce48818c47e6f537b7a3c0d9360a6d51+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_textce48818c47e6f537b7a3c0d9360a6d51='&#117;s&#101;r'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloakce48818c47e6f537b7a3c0d9360a6d51').innerHTML+='<a '+path+'\''+prefix+':'+addyce48818c47e6f537b7a3c0d9360a6d51+'\'>'+addy_textce48818c47e6f537b7a3c0d9360a6d51+'<\/a>';</script>]:
SMTP password? [pa$$word]:
Let's Encrypt account email? (ENTER to skip) [<span id="cloak3f75a3d53e8870d1cc49f7f0d684474f">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak3f75a3d53e8870d1cc49f7f0d684474f').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy3f75a3d53e8870d1cc49f7f0d684474f='m&#101;'+'&#64;';addy3f75a3d53e8870d1cc49f7f0d684474f=addy3f75a3d53e8870d1cc49f7f0d684474f+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text3f75a3d53e8870d1cc49f7f0d684474f='m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak3f75a3d53e8870d1cc49f7f0d684474f').innerHTML+='<a '+path+'\''+prefix+':'+addy3f75a3d53e8870d1cc49f7f0d684474f+'\'>'+addy_text3f75a3d53e8870d1cc49f7f0d684474f+'<\/a>';</script>]:
```

The Discourse setup will create an app.yml file and kick off the bootstrapping process, which can take anywhere from two to eight minutes. Once this portion completes, you can move on to the browser-based setup.

Congrats! You have successfully installed Discourse