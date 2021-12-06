---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install NSQ on Ubuntu**

This guide explains how to setup and Kafka. Below installation steps assume that all the depency packages of Kafka are installed and up to date on your system. Please follow below installation steps. Get kafka by downloading the latest release Kafka and extract it with commands:

    tar -xzf kafka_2.13-2.8.0.tgz
    cd kafka_2.13-2.8.0

Next, start the kafka ENVIRONMENT. You local system environment must have Java 8+ installed. Execute the following commands in order to start all services in the correct order:

    bin/zookeeper-server-start.sh config/zookeeper.properties

Open another terminal session and dtart the Kafka broker service by:

    bin/kafka-server-start.sh config/server.properties

when all services have successfully installed, you will have a basic Kafka environment running and ready to access. You need to create a topic before writing your first event. Open another terminal session and run command:

    bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092

Now, run the console producer client to write a few separate events into the topic:

    bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092

Open another console terminal session and run the console consumer client to read the events you just created with:

    bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092

You can continuously import/export your data into and out of Kafka. Use Ctrl-C to stop the Kafka broker. If you also want to delete any data from your local Kafka environment including any events you have created along the way then run the command:

    rm -rf /tmp/kafka-logs /tmp/zookeeper

Congratulations! You have successfully configured Apache Kafka platform on Ubuntu. Enjoy!
