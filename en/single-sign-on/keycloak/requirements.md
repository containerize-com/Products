---
title: System Requirements
onpagelink: requirements
weight: 1

---

System Requirements
-------------------

- Any OS that runs Java
- Java 8 JDK
- Minimum 512 RAM
- 1 GB of disk space
 
<div class="col-lg-12">Features
--------

 </div><div class="col-lg-12">- Authentication as Service:
- Single Sign-on /Sign-out
- Access Control for API
- Supports Federated Identities (Google,Facebook etc).
- UI Customization
- Multiple Flows (Implicit, Authorization code etc).
- API Authorization
- Claim-based provider
 
 </div><div class="col-lg-12">Installation Instructions
-------------------------

Unzip downloadable distribution file – ‘keycloak-11.0.0.\[zip|tar.gz\]

Standalone Boot Script

/bin directory contains all the scripts. based on the OS the script file can be run:

Linux/Unix

 ```
<pre class="CodeRay highlight">```
$ .../bin/standalone.sh
```
```

Windows

 ```
<pre class="CodeRay highlight">```
> ...\bin\standalone.bat
```
```

Standalone Configuration

Configuration file (in Standalone mode) is located at */standalone/configuration/standalone.xml*.

 </div>### Running in Docker

Start Keycloak with the following command:

 ```
<pre class="highlight">```bash
docker run -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:11.0.0
```
```

 This will start Keycloak exposed on the local port 8080. It will also create an initial admin user with username admin and password admin. ####  

#### **Explore**

You may find the following links relevant:

- **[Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)**
 