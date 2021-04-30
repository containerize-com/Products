---
title: Installation Guide
onpagelink: installation
weight: 3

---



#### **Installation Instructions**

First, run the following command to clone the openchain/docker repository from GitHub:

    git clone https://github.com/openchain/docker.git openchain

Second, run the following commands:

    cd openchaincp templates/docker-compose-direct.yml docker-compose.ymlmkdir datacp templates/config.json data/config.json

Then, edit the configuration file (`data/config.json`):

    nano data/config.json

Finally, set the `instance_seed` setting to a random (non-empty) string.

    [...]   // Define transaction validation parameters   "validator_mode": {     // Required: A random string used to generate the chain namespace     "instance_seed": "",     "validator": { [...] 

In the end, run the following command to start the server:

    docker-compose up -d

