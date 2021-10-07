---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

Run the following command to clone the repo:

    git clone https://github.com/authelia/authelia.git

After successful clone, run the following commands:

    cd authelia/compose/local

    sudo ./setup.sh

sudo is required to modify the /etc/hosts file.

Now, replace example.com with the domain you specified in the setup script and visit the url [https://secure.example.com](https://href.li/?https://secure.example.com).

### Running in Docker

Run the following command to clone the repo:

    git clone https://github.com/authelia/authelia.git

Run the following command after clone:

    cd authelia/compose/lite

Modify the users\_database.yml the default username and password is Authelia

Modify the configuration.yml and docker-compose.yml with your respective domains and secrets

Finally, run the following command to spin up the Docker image:

    docker-compose up -d

