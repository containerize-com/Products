---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install RabbitMQ on Ubuntu**

RabbitMQ is simple and easy to get started software. First, ensure that all the depency packages of RabbitMQ are installed and up to date. Below guide covers RabbitMQ installation on Debian and Ubuntu including distributions based on them. Please follow the instructions below to setup RabbitMQ. Install Erlang with:

    wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb
    sudo dpkg -i erlang-solutions_1.0_all.deb
    sudo apt-get update -y
    sudo apt-get install -y erlang erlang-nox

Next, add RabbitMQ apt repository:

    echo 'deb http://www.rabbitmq.com/debian/ testing main' | sudo tee /etc/apt/sources.list.d/rabbitmq.list
    wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -

update the packages list with command:

    sudo apt-get update -y

Next, install RabbitMQ server:

    sudo apt-get install -y rabbitmq-server

You can start RabbitMQ server using command:

    sudo systemctl start rabbitmq-server

Check RabbitMQ status with:

    sudo systemctl status rabbitmq-server

Enable RabbitMQ service so it starts on system boot:

    sudo systemctl enable rabbitmq-server

Next, setup RabbitMQ web management console: 

    sudo rabbitmq-plugins enable rabbitmq_management

Create administrator account in RabbitMQ single instance:

    sudo rabbitmqctl add_user admin password 
    sudo rabbitmqctl set_user_tags admin administrator
    sudo rabbitmqctl set_permissions -p / admin ".*" ".*" ".*"

You can setup RabbitMQ instance cluster on the master node with:

    wget https://gist.githubusercontent.com/fernandoaleman/05cbf15e0e58f8de7a29a21b24f9debb/raw/55efa7b36c245a9f6ffa3bcd2382c078cce0e9a2/rabbitmq-cluster.sh
    chmod +x rabbitmq-cluster.sh
    ./rabbitmq-cluster.sh

Open your favourite browser and browse http://localhost:15672/ for opening the rabbitmq management.

Congratulations! You have successfully installed RabbitMQ software on ubuntu 20.04. Enjoy!
