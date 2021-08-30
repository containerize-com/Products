---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

## Install Shuup On Ubuntu

First, ensure that all the depency packages of Shuup multivendor store are installed and up to date. Fastest way to get Shuup up and running is to use Docker:

    docker-compose up

Open localhost:8000/sa web panel in your favourite browser. Default log in with username: admin password: admin. If you want to install Shuup on local development environment then follow below guide. Update pip and setuptools below:

    pip install -U pip
    pip install -U setuptools

Now, set up a new virtualenv for Shuup and activate it using command:

    pip install -U pip
    pip install -U setuptools

Next, install shuup via pypi python packaging:

    pip install shuup

Once installed, you can begin setting up a Django project, settings and urls for configuration details. You will also need to add shuup.core to your INSTALLED_APPS. Finally, once you have configured the Shuup application then run the following commands to create the database and initialize Shuup:

    python manage.py migrate
    python manage.py shuup_init

Congratulations! You have now set up the Shuup open source marketplace. Enjoy!