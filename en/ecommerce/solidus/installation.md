---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Solidus on Linux (Debian-based)

Making sure you have Imagemagick installed, which is required for Paperclip.To add solidus, begin with a Rails 5/6 application and a database configured and created. Clone the Git repo and install the gem dependencies.

 ```
git clone git://github.com/solidusio/solidus.git
cd solidus
bin/setup
```

For Solidus v2.11 and above, Add the following to your Gemfile.

 ```
gem 'solidus'
```

Run the bundle command to install.

 ```
bundle install
```

After installing gems, you'll have to run the generator to create necessary configuration files and migrations.

 ```
bin/rails g solidus:install
```

Start the Rails server with the command to access solidus store

 ```
bin/rails s
```

The solidus\_frontend storefront will be accessible at http://localhost:3000/ and the admin can be found at http://localhost:3000/admin/.

You may notice that your Solidus store runs slowly in development mode. This can be because in development each CSS and JavaScript is loaded as a separate include. This can be disabled by adding the following to config/environments/development.rb.

 ```
Rails.application.configure do
  config.assets.debug = false
end
```

The default user and password are <span id="cloaka238214f466ab0b45f1cacafae78bd98">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloaka238214f466ab0b45f1cacafae78bd98').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addya238214f466ab0b45f1cacafae78bd98='&#97;dm&#105;n'+'&#64;';addya238214f466ab0b45f1cacafae78bd98=addya238214f466ab0b45f1cacafae78bd98+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_texta238214f466ab0b45f1cacafae78bd98='&#97;dm&#105;n'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloaka238214f466ab0b45f1cacafae78bd98').innerHTML+='<a '+path+'\''+prefix+':'+addya238214f466ab0b45f1cacafae78bd98+'\'>'+addy_texta238214f466ab0b45f1cacafae78bd98+'<\/a>';</script> and test123, respectively. There are also options and rake tasks provided by solidus\_auth\_devise.

Congratulations! You have successfully installed Solidus store and now customize any of the built-in features to your heart's desire.