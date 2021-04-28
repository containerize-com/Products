---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installation using Github

First make sure you have installed all the dependencies. Clone the latest Phabricator and dependencies from github into document root folder::

 ```
<pre class="command">```
git clone https://github.com/phacility/libphutil.git
git clone https://github.com/phacility/arcanist.git
git clone https://github.com/phacility/phabricator.git

```
```

Navigate to the phabricator directory:

 ```
<pre class="command">```
cd  phabricator

```
```

Run following commands to configure MySQL configuration file:

 ```
<pre class="command">```
./bin/config set mysql.host localhost
./bin/config set mysql.user root
./bin/config set mysql.pass MySQL_root_password

```
```

Load the Phabricator schema by executing the following command:

 ```
<pre class="command">```
./bin/storage upgrade

Are you ready to continue? [y/N] y

Applying schema adjustments...
Done.
Completed applying all schema adjustments.
 ANALYZE  Analyzing tables...
Done.
 ANALYZED  Analyzed 510 table(s).

```
```

Configure Virtual host for Apache or Nginx. Finally, open your web browser and navigate to http://phabricator.yourdomain.com or as per your virtual host settings.