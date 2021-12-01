---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Hypercable on Ubuntu**

Install and configure the necessary dependencies packages. Hypercable business intelligence solution is easy to setup and get started. To get started with Hypercable business intelligence and analytics, clone the repo to your computer or server

    git clone https://github.com/HyperCable/hypercable.git
    cd hypercable

To setup production hypercable bi product environment please follow below steps. Setup production environment

    edit .env.production

Migrate rails migrations to populate production database

    docker-compose -f docker-compose.production.yaml run rails rake db:migrate

Run sidekiq job scheduler to handle many jobs at the same time and then setup docker production image

    docker-compose -f docker-compose.production.yaml up -d --scale sidekiq=6
    git pull && docker-compose -f docker-compose.production.yaml pull
    docker-compose -f docker-compose.production.yaml logs --tail="100"

Congratulations! You have successfully installed Hypercable open source bi tool. Enjoy!