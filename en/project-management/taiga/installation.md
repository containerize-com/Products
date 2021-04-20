---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

First make sure you have installed all the dependencies. Clone the latest taiga-back from github into document root folder:

 ```
<pre class="command">```
git clone https://github.com/taigaio/taiga-back.git taiga-back
cd taiga-back
git checkout stable

```
```

Create a new virtualenv named taiga:

 ```
<pre class="command">```
mkvirtualenv -p /usr/bin/python3 taiga

```
```

Install all Python dependencies:

 ```
<pre class="command">```
pip install -r requirements.txt

```
```

Execute all migrations to populate the database with basic necessary initial data:

 ```
<pre class="command">```
python manage.py migrate --noinput
python manage.py loaddata initial_user
python manage.py loaddata initial_project_templates
python manage.py compilemessages
python manage.py collectstatic --noinput

```
```

The above migrations create an administrator account. The login credentials are the following: username: admin password: 123123

To finish the setup of taiga-back, create the initial configuration file for proper static/media file resolution, optionally with email sending support:

Copy-paste the following config into ~/taiga-back/settings/local.py and update it with your own details:

 ```
<pre class="command">```
from .common import *

MEDIA_URL = "http://example.com/media/"
STATIC_URL = "http://example.com/static/"
SITES["front"]["scheme"] = "http"
SITES["front"]["domain"] = "example.com"

SECRET_KEY = "theveryultratopsecretkey"

DEBUG = False
PUBLIC_REGISTER_ENABLED = True

DEFAULT_FROM_EMAIL = "<span id="cloakf0662ef186022826bc7badf6be14fe38">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloakf0662ef186022826bc7badf6be14fe38').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addyf0662ef186022826bc7badf6be14fe38='n&#111;-r&#101;ply'+'&#64;';addyf0662ef186022826bc7badf6be14fe38=addyf0662ef186022826bc7badf6be14fe38+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_textf0662ef186022826bc7badf6be14fe38='n&#111;-r&#101;ply'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloakf0662ef186022826bc7badf6be14fe38').innerHTML+='<a '+path+'\''+prefix+':'+addyf0662ef186022826bc7badf6be14fe38+'\'>'+addy_textf0662ef186022826bc7badf6be14fe38+'<\/a>';</script>"
SERVER_EMAIL = DEFAULT_FROM_EMAIL

#CELERY_ENABLED = True

EVENTS_PUSH_BACKEND = "taiga.events.backends.rabbitmq.EventsPushBackend"
EVENTS_PUSH_BACKEND_OPTIONS = {"url": "amqp://taiga:PASSWORD_FOR_EVENTS@localhost:5672/taiga"}

# Uncomment and populate with proper connection parameters
# to enable email sending. `EMAIL_HOST_USER` should end by @.
#EMAIL_BACKEND = "django.core.mail.backends.smtp.EmailBackend"
#EMAIL_USE_TLS = False
#EMAIL_HOST = "localhost"
#EMAIL_HOST_USER = ""
#EMAIL_HOST_PASSWORD = ""
#EMAIL_PORT = 25

# Uncomment and populate with proper connection parameters
# to enable GitHub login/sign-in.
#GITHUB_API_CLIENT_ID = "yourgithubclientid"
#GITHUB_API_CLIENT_SECRET = "yourgithubclientsecret"

```
```

Download the frontend code from GitHub:

 ```
<pre class="command">```
cd ~
git clone https://github.com/taigaio/taiga-front-dist.git taiga-front-dist
cd taiga-front-dist
git checkout stable

```
```

Copy the example config file:

 ```
<pre class="command">```
cp ~/taiga-front-dist/dist/conf.example.json ~/taiga-front-dist/dist/conf.json

```
```

Edit the example configuration following the pattern below (replace with your own details):

 ```
<pre class="command">```
{
	"api": "http://example.com/api/v1/",
	"eventsUrl": "ws://example.com/events",
	"debug": "true",
	"publicRegisterEnabled": true,
	"feedbackEnabled": true,
	"privacyPolicyUrl": null,
	"termsOfServiceUrl": null,
	"GDPRUrl": null,
	"maxUploadFileSize": null,
	"contribPlugins": []
}

```
```

Having taiga-front-dist downloaded and configured is insufficient. The next step is to expose the code (in dist directory) under a static file web server.