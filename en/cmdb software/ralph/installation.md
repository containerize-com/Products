---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing using Docker

Once you have installed the pre-requisites, make a new empty directory and create ‘docker-compose.yml’ file and populate it with [this](https://raw.githubusercontent.com/allegro/ralph/ng/docker/docker-compose.yml) data.

Now, run the following command to make build.

 ```
docker-compose build
```

After that, run the following command to initialize database run:

 ```
docker-compose run –rm web /root/init.sh
```

Then, run the following command to spin up the docker container:

 ```
docker-compose up -d
```
Finally, access the application in the browser at this address. http://127.0.0.1
