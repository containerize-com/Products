---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

First, run the following commands to clone the repository.

 ```

git clone https://github.com/metasfresh/metasfresh-docker.git
cd metasfresh-docker/

```

After that, open ocker-compose.yml file. Replace http://example.com:8080 with your domain and also comment out it.

Build the Docker container.

 ```
docker-compose build
```

Finally, start the Docker container.

 ```
docker-compose up -d
```

After the successful installation, access the application.

