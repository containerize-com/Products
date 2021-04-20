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
Email address for admin account(s)? [<span id="cloak854e61d0c65c74fdfa9f61e8cb990109">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak854e61d0c65c74fdfa9f61e8cb990109').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy854e61d0c65c74fdfa9f61e8cb990109='m&#101;'+'&#64;';addy854e61d0c65c74fdfa9f61e8cb990109=addy854e61d0c65c74fdfa9f61e8cb990109+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text854e61d0c65c74fdfa9f61e8cb990109='m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak854e61d0c65c74fdfa9f61e8cb990109').innerHTML+='<a '+path+'\''+prefix+':'+addy854e61d0c65c74fdfa9f61e8cb990109+'\'>'+addy_text854e61d0c65c74fdfa9f61e8cb990109+'<\/a>';</script>,<span id="cloakcd455dd616fab6575709500616b4ed7a">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloakcd455dd616fab6575709500616b4ed7a').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addycd455dd616fab6575709500616b4ed7a='y&#111;&#117;'+'&#64;';addycd455dd616fab6575709500616b4ed7a=addycd455dd616fab6575709500616b4ed7a+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_textcd455dd616fab6575709500616b4ed7a='y&#111;&#117;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloakcd455dd616fab6575709500616b4ed7a').innerHTML+='<a '+path+'\''+prefix+':'+addycd455dd616fab6575709500616b4ed7a+'\'>'+addy_textcd455dd616fab6575709500616b4ed7a+'<\/a>';</script>]:
SMTP server address? [smtp.example.com]:
SMTP port? [587]:
SMTP user name? [<span id="cloak5f0eff1d191a2c03b58ff279ad890087">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak5f0eff1d191a2c03b58ff279ad890087').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy5f0eff1d191a2c03b58ff279ad890087='&#117;s&#101;r'+'&#64;';addy5f0eff1d191a2c03b58ff279ad890087=addy5f0eff1d191a2c03b58ff279ad890087+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text5f0eff1d191a2c03b58ff279ad890087='&#117;s&#101;r'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak5f0eff1d191a2c03b58ff279ad890087').innerHTML+='<a '+path+'\''+prefix+':'+addy5f0eff1d191a2c03b58ff279ad890087+'\'>'+addy_text5f0eff1d191a2c03b58ff279ad890087+'<\/a>';</script>]:
SMTP password? [pa$$word]:
Let's Encrypt account email? (ENTER to skip) [<span id="cloak2303800736e78241ddf93bf8d0c6d59e">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak2303800736e78241ddf93bf8d0c6d59e').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy2303800736e78241ddf93bf8d0c6d59e='m&#101;'+'&#64;';addy2303800736e78241ddf93bf8d0c6d59e=addy2303800736e78241ddf93bf8d0c6d59e+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text2303800736e78241ddf93bf8d0c6d59e='m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak2303800736e78241ddf93bf8d0c6d59e').innerHTML+='<a '+path+'\''+prefix+':'+addy2303800736e78241ddf93bf8d0c6d59e+'\'>'+addy_text2303800736e78241ddf93bf8d0c6d59e+'<\/a>';</script>]:
```

The Discourse setup will create an app.yml file and kick off the bootstrapping process, which can take anywhere from two to eight minutes. Once this portion completes, you can move on to the browser-based setup.

Congrats! You have successfully installed Discourse