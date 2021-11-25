---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Apache Spark on Ubuntu 18.04**

Execute command to download Apache Spark.

 ```
$ wget https://archive.apache.org/dist/spark/spark-3.1.1/spark-3.1.1-bin-hadoop3.2.tgz
```

Extract the tar file using below command.

 ```
$ tar -zxf spark-3.1.1-bin-hadoop3.2.tgz
```

Move the extracted directory.

 ```
$ sudo mv spark-3.1.1-bin-hadoop3.2 /opt/spark
```

Open .bashrc file and add below lines into it.

 ```
export SPARK_HOME=/opt/spark
export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin
```

Activate the environment with the following command.

 ```
$ source ~/.bashrc
```

Start the Spark master server.

 ```
$ start-master.sh
```

Open browser and enter http://server-ip:8080 for accessing the web interface.
