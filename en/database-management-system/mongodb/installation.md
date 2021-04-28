---
title: Installation
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Follow these steps to Install MongoDB on Ubuntu 18.04:

- To import the public GPG key for the latest version of MongoDB, run following command:
 
 ```
curl -fsSL https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
```

- Change 4.4 from URL if you want to install another version.
- It should return "OK" after successful key creation.
 
- After adding repository now update your system apt using:
 
 ```
sudo apt update
```

- Now install MongoDB using following command:
 
 ```
sudo apt install mongodb-org
```

- Run following command to start the MongoDB service:
 
 ```
sudo systemctl start mongod.service
```

- Then check the MongoDB status:
 
 ```
sudo systemctl status mongod
```