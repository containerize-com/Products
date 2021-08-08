---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

### Install Celery on Ubuntu

Celery is simple and easy to get started software. First, ensure that all the depency packages of Celery are installed and up to date. Below guide covers Celery installation on Debian and Ubuntu including distributions based on them. Please follow the instructions below to setup Celery. Update your system with command:

sudo apt update && sudo apt upgrade

Next, install celery by running command:

pip install -U celery

If you’re installing RabbitMQ on Ubuntu or Debian then execute this command:

sudo apt-get install rabbitmq-server

If you’re using Redis as the backend so make sure You install Redis via apt on Ubuntu by command:

sudo apt-get install redis-server

Additionally, Celery defines a single or a group of bundles that can be used to install Celery and the required dependencies with command:

pip install "celery[librabbitmq]"
pip install "celery[librabbitmq,redis,auth,msgpack]"

For a complete list of the command line options please run:

celery worker --help
celery --help

For RabbitMQ you can use amqp://localhost or for Redis you can use redis://localhost.

Congratulations! You have successfully installed Celery software on ubuntu. Enjoy!