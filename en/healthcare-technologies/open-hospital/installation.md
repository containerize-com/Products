---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once pre-requisites are setup, clone the source code by running the following command:

    git clone https://github.com/informatici/openhospital-core.git

After that, run the following command:

    mvn package

Then, install the dependencies

    mvn install

Finally, spin up the Docker container with the following command:

    docker-compose up

