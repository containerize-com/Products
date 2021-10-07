---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing using downloaded package:

Download the latest release from https://craterapp.com/downloads.

Upload the downloaded zip file to your Server and unzip it.

Point your domain or subdomain to the public directory inside the Crater directory.

Open your web browser and go to your given domain and follow the installation wizard.

#### Installing using Docker:

Install Docker and docker-compose on your server.

Clone the repository by running this command.

 ```
$ git clone https://github.com/bytefury/crater
```

Change your current working directory and run your application using below commands.

 ```

$ cd crater
$ cp .env.example .env
$ docker-compose up -d
$ ./docker-compose/setup.sh

```

Open your web browser and go to your given domain and follow the installation wizard.

