---
title: Installation
onpagelink: installation
weight: 3

---

Installation
------------

This guide will install the Psono server, and runs it with gunicorn and nginx. It has been tested on Ubuntu 18.04.

- Become root
 
 ```
sudo su
```

- Install some generic stuff
 
 ```
apt-get update
apt-get install -y \
        git \
        libyaml-dev \
        libpython3-dev \
        libpq-dev \
        libffi-dev \
        python3-dev \
        python-pip \
        python3-pip \
        python3-psycopg2 \
        postgresql-client \
        haveged \
        libsasl2-dev \
        libldap2-dev \
        libssl-dev \
        supervisor
pip3 install gunicorn
```

- Create psono user
 
 ```
adduser psono
```

- Become the psono user
 
 ```
su psono
```

- Clone git repository
 
 ```
git clone https://gitlab.com/psono/psono-server.git ~/psono-server
```

- Install python requirements
 
 ```
Ctrl + D
cd /home/psono/psono-server
pip3 install -r requirements.txt
su psono
```

- Create settings folder
 
 ```
mkdir ~/.psono_server
```

- Create a settings.yaml in ~/.psono\_server/ with the following content
 
 ```

# generate the following six parameters with the following command
# python3 ~/psono-server/psono/manage.py generateserverkeys
SECRET_KEY: 'SOME SUPER SECRET KEY THAT SHOULD BE RANDOM AND 32 OR MORE DIGITS LONG'
ACTIVATION_LINK_SECRET: 'SOME SUPER SECRET ACTIVATION LINK SECRET THAT SHOULD BE RANDOM AND 32 OR MORE DIGITS LONG'
DB_SECRET: 'SOME SUPER SECRET DB SECRET THAT SHOULD BE RANDOM AND 32 OR MORE DIGITS LONG'
EMAIL_SECRET_SALT: '$2b$12$XUG.sKxC2jmkUvWQjg53.e'
PRIVATE_KEY: '302650c3c82f7111c2e8ceb660d32173cdc8c3d7717f1d4f982aad5234648fcb'
PUBLIC_KEY: '02da2ad857321d701d754a7e60d0a147cdbc400ff4465e1f57bc2d9fbfeddf0b'

# The URL of the web client (path to e.g activate.html without the trailing slash)
# WEB_CLIENT_URL: 'https://www.psono.pw'

# Switch DEBUG to false if you go into production
DEBUG: False

# Adjust this according to Django Documentation https://docs.djangoproject.com/en/2.2/ref/settings/
ALLOWED_HOSTS: ['*']

# Should be your domain without "www.". Will be the last part of the username
ALLOWED_DOMAINS: ['psono.pw']

# If you want to disable registration, you can comment in the following line
# ALLOW_REGISTRATION: False

# If you want to disable the lost password functionality, you can comment in the following line
# ALLOW_LOST_PASSWORD: False

# If you want to enforce that the email address and username needs to match upon registration
# ENFORCE_MATCHING_USERNAME_AND_EMAIL: False

# If you want to restrict registration to some email addresses you can specify here a list of domains to filter
# REGISTRATION_EMAIL_FILTER: ['company1.com', 'company2.com']

# Should be the URL of the host under which the host is reachable
# If you open the url and append /info/ to it you should have a text similar to {"info":"{\"version\": \"....}
HOST_URL: 'https://www.psono.pw/server'

# The email used to send emails, e.g. for activation
# ATTENTION: If executed in a docker container, then "localhost" will resolve to the docker container, so
# "localhost" will not work as host. Use the public IP or DNS record of the server.
EMAIL_FROM: <span id="cloak820118571330d66e81d06c4c2b562de4">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak820118571330d66e81d06c4c2b562de4').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy820118571330d66e81d06c4c2b562de4='&#039;th&#101;-m&#97;&#105;l-f&#111;r-f&#111;r-&#101;x&#97;mpl&#101;-&#117;s&#101;r&#97;cc&#111;&#117;nt-&#97;ct&#105;v&#97;t&#105;&#111;ns'+'&#64;';addy820118571330d66e81d06c4c2b562de4=addy820118571330d66e81d06c4c2b562de4+'t&#101;st'+'&#46;'+'c&#111;m';var addy_text820118571330d66e81d06c4c2b562de4='&#039;th&#101;-m&#97;&#105;l-f&#111;r-f&#111;r-&#101;x&#97;mpl&#101;-&#117;s&#101;r&#97;cc&#111;&#117;nt-&#97;ct&#105;v&#97;t&#105;&#111;ns'+'&#64;'+'t&#101;st'+'&#46;'+'c&#111;m';document.getElementById('cloak820118571330d66e81d06c4c2b562de4').innerHTML+='<a '+path+'\''+prefix+':'+addy820118571330d66e81d06c4c2b562de4+'\'>'+addy_text820118571330d66e81d06c4c2b562de4+'<\/a>';</script>'
EMAIL_HOST: 'localhost'
EMAIL_HOST_USER: ''
EMAIL_HOST_PASSWORD : ''
EMAIL_PORT: 25
EMAIL_SUBJECT_PREFIX: ''
EMAIL_USE_TLS: False
EMAIL_USE_SSL: False
EMAIL_SSL_CERTFILE:
EMAIL_SSL_KEYFILE:
EMAIL_TIMEOUT:

# In case one wants to use mailgun, comment in below lines and provide the mailgun access key and server name
# EMAIL_BACKEND: 'anymail.backends.mailgun.EmailBackend'
# MAILGUN_ACCESS_KEY: ''
# MAILGUN_SERVER_NAME: ''

# In case you want to offer Yubikey support, create a pair of credentials here https://upgrade.yubico.com/getapikey/
# and update the following two lines before commenting them in
# YUBIKEY_CLIENT_ID: '123456'
# YUBIKEY_SECRET_KEY: '8I65IA6ASDFIUHGIH5021FKJA='

# If you have own Yubico servers, you can specify here the urls as a list
# YUBICO_API_URLS: ['https://api.yubico.com/wsapi/2.0/verify']

# Cache enabled without belows Redis may lead to unexpected behaviour

# Cache with Redis
# By default you should use something different than database 0 or 1, e.g. 13 (default max is 16, can be configured in
# redis.conf) possible URLS are:
#    redis://[:password]@localhost:6379/0
#    rediss://[:password]@localhost:6379/0
#    unix://[:password]@/path/to/socket.sock?db=0
# CACHE_ENABLE: False
# CACHE_REDIS: False
# CACHE_REDIS_LOCATION: 'redis://127.0.0.1:6379/13'

# Disables Throttling (necessary for unittests to pass) by overriding the cache with a dummy cache
# https://docs.djangoproject.com/en/2.2/topics/cache/#dummy-caching-for-development
# THROTTLING: False

# Enables the management API, required for the psono-admin-client / admin portal
# MANAGEMENT_ENABLED: False

# Enables the fileserver API, required for the psono-fileserver
# FILESERVER_HANDLER_ENABLED: False

# Enables files for the client
# FILES_ENABLED: False

# Allows that users can search for partial usernames
# ALLOW_USER_SEARCH_BY_USERNAME_PARTIAL: True

# Allows that users can search for email addresses too
# ALLOW_USER_SEARCH_BY_EMAIL: True

# Disables central security reports
# DISABLE_CENTRAL_SECURITY_REPORTS: True

# Configures a system wide DUO connection for all clients
# DUO_INTEGRATION_KEY: ''
# DUO_SECRET_KEY: ''
# DUO_API_HOSTNAME: ''

# If you are using the DUO proxy, you can configure here the necessary HTTP proxy
# DUO_PROXY_HOST: 'the-ip-or-dns-name-goes-here'
# DUO_PROXY_PORT: 80
# DUO_PROXY_TYPE: 'CONNECT'
# If your proxy requires specific headers you can also configure these here
# DUO_PROXY_HEADERS: ''

# Normally only one of the configured second factors needs to be solved. Setting this to True forces the client to solve all
# MULTIFACTOR_ENABLED: True

# Allows admins to limit the offered second factors in the client
# ALLOWED_SECOND_FACTORS: ['yubikey_otp', 'google_authenticator', 'duo']

# Your Postgres Database credentials
# ATTENTION: If executed in a docker container, then "localhost" will resolve to the docker container, so
# "localhost" will not work as host. Use the public IP or DNS record of the server.
DATABASES:
    default:
        'ENGINE': 'django.db.backends.postgresql_psycopg2'
        'NAME': 'psono'
        'USER': 'psono'
        'PASSWORD': 'password'
        'HOST': 'localhost'
        'PORT': '5432'
# for master / slave replication setup comment in the following (all reads will be redirected to the slave
#    slave:
#        'ENGINE': 'django.db.backends.postgresql_psycopg2'
#        'NAME': 'YourPostgresDatabase'
#        'USER': 'YourPostgresUser'
#        'PASSWORD': 'YourPostgresPassword'
#        'HOST': 'YourPostgresHost'
#        'PORT': 'YourPostgresPort'

# Update the path to your templates folder
# If you do not want to change it (yet) you can leave it like it is.
TEMPLATES: [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['/home/psono/psono-server/psono/templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]	

```

*   Update database credentials / secrets / paths like described in the comments above.
*   To send a test e-mail to <span id="cloak21ede15124b07fd7b5389d8817baeb74">[something@something.com](mailto:something@something.com)</span> execute:
        
        
        python3 ~/psono-server/psono/manage.py sendtestmail something@something.com
        

- If you receive this test e-mail, e-mail should be configured proper.
- Create our database
 
 ```
python3  ~/psono-server/psono/manage.py migrate
```

- Run the psono server
 
 ```
cd ~/psono-server/psono
gunicorn --bind 0.0.0.0:10100 wsgi
```

- This will start the Psono server on port 10100. If you open now http://your-ip:10100/info/ should see something like this:
 
 ```
{"info":"{\"version\": \"....}
```

- Become root again
 
 ```
Ctrl + D
```

- Create supervisor config. Create a psono-server.conf in /etc/supervisor/conf.d/ with the following content:
 
 ```
[program:psono-server]
command = /usr/local/bin/gunicorn --bind 127.0.0.1:10100 wsgi
directory=/home/psono/psono-server/psono
user = psono
autostart=true
autorestart=true
redirect_stderr=true
```

- You may have realised that we changed the bind. This way Psono is only accessible from localhost, which is fine as we will proxy requests with nginx.
- Reload supervisorctl
 
 ```
supervisorctl reload
```

- Setup cleanup job
 
 ```
crontab -e
```

- and add the following line:
 
 ```
30 2 * * * psono python3 /home/psono/psono-server/psono/manage.py cleartoken >> /var/log/cron.log 2>&1
```

- To run the Psono password manager in production, a reverse proxy is needed, to handle the ssl offloading and glue the psono server and webclient together. Follow the guide to [setup reverse proxy](https://doc.psono.com/admin/installation/install-reverse-proxy.html) as a next step.
 