---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing by downloading Binary

Download the latest release and extract the listmonk binary.

Generate config.toml by using below command and then edit file.

 ```
./listmonk –new-config
```

Use below command to install PostgreSQL.

 ```
./listmonk –install
```

Run below command, open your browser and visit http://localhost:9000

 ```
./listmonk
```

### Installing using Docker

The latest image is available on DockerHub at listmonk/listmonk:latest

Use sample docker-compose.yml to run listmonk and PostgreSQL by following below command.

 ```

docker-compose up db
docker-compose run –rm app ./listmonk

```

Use following command to Run the app.

 ```
docker-compose up app
```

Now, open your browser and visit http://localhost:9000

#### **Explore**

You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
 