---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

Unzip downloadable distribution file –  ‘keycloak-11.0.0.\[zip|tar.gz\]

Standalone Boot Script

/bin directory contains all the scripts. based on the OS the script file can be run:

Linux/Unix

    $ .../bin/standalone.sh

Windows

    > ...\bin\standalone.bat

Standalone Configuration

Configuration file (in Standalone mode) is located at _/standalone/configuration/standalone.xml_.

### Running in Docker

Start Keycloak with the following command:

    docker run -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:11.0.0

This will start Keycloak exposed on the local port 8080. It will also create an initial admin user with username admin and password admin.

