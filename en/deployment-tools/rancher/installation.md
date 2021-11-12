---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing using Ubuntu

Run below command to install Rancher server.

 ```
$ sudo docker run -d --restart=always -p 8080:8080 rancher/server:v1.0.2
```

Open browser and enter http://SERVER\_IP\_ADDRESS:8080. It will load web UI. Now, user can start adding hosts.

Execute the following command for launching Rancher server by bind mounting the MySQL volume.

 ```
$ sudo docker run -d -v :/var/lib/mysql --restart=always -p 8080:8080 rancher/server:v1.0.2
```

