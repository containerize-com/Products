---
title: System Requirements
onpagelink: requirements
weight: 1

---

### **System Requirements**

Orbeon Forms runs on any platform that supports:

- A Java runtime
- a Servlet 2.5 (or greater) container such as Apache Tomcat. For versions supported, see Tomcat.
 
#### Hardware requirements

We recommend you run Orbeon Forms on a dedicated server or instance that satisfies the following requirements:

- CPU: recent 4-core, or more, Intel Xeon or Core i7 or newer. We don't recommend AMD CPUs (prior to the Ryzen line).
- RAM: 4 GB of RAM, or more, available to the Java Virtual Machine (JVM heap size).
 
If using AWS EC2, we recommend you start with a c4.2xlarge instance. For most projects, it is safe to start with a configuration along those lines, but you might want to have more powerful or multiple servers or instances (or equivalent) for situations calling for high availability, or to handle more load. When running Orbeon Forms PE on multiple servers or instances, you need one PE subscription per server or instance. For more details on sizing, see the section on how much load Orbeon Forms can handle.
