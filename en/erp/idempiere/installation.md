---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installing using Docker

Get latest image from hub.docker.com.

 ```
docker pull idempiereofficial/idempiere
```

Run the following command to setup PostgreSQL database server.

 ```
docker run -d --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=postgres postgres:13
```

Execute below command to setup iDempiere.

 ```
docker run -d --name idempiere -p 8080:8080 --link postgres:postgres idempiereofficial/idempiere:8.2
```

Open the site http://example.com:8080/webui/ and follow installation wizard.