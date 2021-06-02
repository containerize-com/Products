---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### **Install Apache Storm on Ubuntu 18.04**

#### Install ZooKeeper Framework

First, install ZooKeeper framework on the server. Create directory and navigate into it.

 ```
$ mkdir ~/bigdata
$ cd ~/bigdata
```

Execute command to download ZooKeeper framework.

 ```
$ wget https://downloads.apache.org/zookeeper/zookeeper-3.6.0/apache-zookeeper-3.6.0-bin.tar.gz
```

Extract the files and change directory by running below commands.

 ```
$ tar xfvz apache-zookeeper-3.6.0-bin.tar.gz
$ cd apache-zookeeper-3.6.0-bin.tar.gz
```

Copy sample configuration file with the new name.

 ```
$ cp conf/zoo_sample.cfg conf/zoo.cfg
```

Open conf/zoo.cfg file and add the following code into it.

 ```
admin.enableServer=true
admin.serverPort=9990
```

Run command to start Zookeeper.

 ```
$ bin/zkServer.sh start
```

#### Install Apache Storm

Execute command to download Apache Storm.

 ```
$ wget ftp://apache.uib.no/pub/apache/storm/apache-storm-2.1.0/apache-storm-2.1.0.tar.gz
```

Extract the tar file and change directory using below commands.

 ```
$ tar -zxf apache-storm-2.1.0.tar.gz
$ cd apache-storm-2.1.0
```

Open conf/storm.yaml file and add below lines into it.

 ```
storm.zookeeper.servers:
 - "localhost"
nimbus.seeds: [ "localhost" ]
```

Run command to start the Nimbus.

 ```
$ bin/storm nimbus
```

Start the Supervisor by running below command.

 ```
$ bin/storm supervisor
```

Start the UI.

 ```
$ bin/storm ui
```

Open your browser and enter http://localhost:8080 to access the storm cluster information and its running topology.