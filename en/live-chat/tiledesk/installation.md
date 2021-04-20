---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation via Docker Compose

Run Docker Compose services using the following code:

 ```
mkdir tiledesk && cd tiledesk
curl https://raw.githubusercontent.com/Tiledesk/tiledesk-server/master/docker-compose.yml --output docker-compose.yml
curl https://raw.githubusercontent.com/Tiledesk/tiledesk-server/master/.env.sample --output .env

```

Start all the Tiledesk services just typing:

 ```
docker-compose up -d
```