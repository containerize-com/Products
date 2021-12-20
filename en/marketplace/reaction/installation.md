---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

## Install Reaction On Ubuntu

First, ensure that all the depency packages of Reaction are installed and  up to date then please follow the instructions listed below. Clone reactioncommerce repository, and then run make command in the reaction-development-platform directory as below: 

    git clone git@github.com:reactioncommerce/reaction-development-platform.git
    cd reaction-development-platform
    make

It will take some time to download and start all of the components for the entire Reaction application running on your computer through Docker. Individual services are cloned as child directories and make checks that dependencies are present.

Make clones subprojects from GitHub, downloads Docker images and start all services. Services will be running after the initial make is completed. If the make command fails at some point of setup then you can rerun it for specific service e.g example-storefront using:

    make init-<project-name>
    make init-example-storefront

These are many make commands available in the reaction platform root directory and the development platform runs the latest version of Reaction by default. After the make command completes provisioning the system, you can create a shop manager account on your local development instance, access dashboard, playground, and storefronts.

Next, browse Open Commerce login page interface for administrators and shop managers at localhost:4080. Register your account and configure shops to manage product orders from the Open Commerce admin dashboard. You can visit the GraphQL playground at localhost:3000/graphql. You can also view your Open Commerce storefront built with Next.JS at http://localhost:4000

Congratulations! You have now set up the Reaction Commerce successfully. Enjoy!