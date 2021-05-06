---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Installing using Docker

Run below commands to install Concourse server with Docker compose.

 ```

$ wget https://concourse-ci.org/docker-compose.yml
$ docker-compose up -d

```

Open browser and enter http://localhost:8080 for accessing web UI. Login with username/password as test/test.

Execute the following command for installing fly CLI and use test user for login.

 ```
$ fly -t tutorial login -c http://localhost:8080 -u test -p test
```