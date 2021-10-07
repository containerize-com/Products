---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation via Snap on Ubuntu**

Installing a snap on Ubuntu is as easy as

 ```
sudo snap install rocketchat-server

```

Then browse to `http://localhost:3000` and setup Rocket.Chat.

Snaps are secure. Rocket.Chat and all of its dependencies are isolated from the rest of your system. Snaps also auto update when we release a new version. So no need more hassle updating.

On Ubuntu 16.04LTS, install snapd first:

 ```
sudo apt-get install snapd 
```

### Installation via Docker

First, start an instance of mongo and initiate replicaSet:

 ```
$ docker run --name db -d mongo:4.0 --smallfiles --replSet rs0 --oplogSize 128
$ docker exec -ti db mongo --eval "printjson(rs.initiate())"

```

Then start Rocket.Chat linked to this mongo instance:

 ```
$ docker run --name rocketchat --link db --env MONGO_OPLOG_URL=mongodb://db:27017/local -d rocket.chat

```

This will start a Rocket.Chat instance listening on the default Meteor port of 3000 on the container.  
 If you’d like to be able to access the instance directly at standard port on the host machine:

 ```
$ docker run --name rocketchat -p 80:3000 --link db --env ROOT_URL=http://localhost --env MONGO_OPLOG_URL=mongodb://db:27017/local -d rocket.chat
```

Then, access it via http://localhost in a browser. Replace localhost in ROOT\_URL with your own domain name if you are hosting at your own domain.  
 If you’re using a third party Mongo provider, or working with Kubernetes, you need to override the MONGO\_URL environment variable:

 ```
$ docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --env MONGO_URL=mongodb://mymongourl/mydb --env MONGO_OPLOG_URL=mongodb://mymongourl:27017/local -d rocket.chat
```
