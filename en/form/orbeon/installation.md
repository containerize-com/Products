---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Java virtual machine configuration

Configure the Java VM with:

- -Xmx option for dedicated Java heap memory: 
  - on a development machine: at least 1 GB of Java heap: -Xmx1g
  - on a production machine: at least 4 GB of Java heap: -Xmx4g
- -XX:MaxPermSize for "permgen" space (Java 1.7): 
  - use at least: -XX:MaxPermSize=256m
 
 
Also, make sure that you do not have tiered compilation when using Java 7

NOTE: On Unix systems, GIJ / GCG is not supported as there are reports of issues with that runtime environment and Orbeon Forms. Instead, we recommend you use the Oracle runtime Java environment.

#### Database setup

Out-of-the-box, forms you create with Form Builder, as well as data captured with those forms, will be saved in an embedded database called eXist. You can setup Orbeon Forms so this data gets stored in your relational database, but if you're getting started with Orbeon Forms, you might to just use the embedded eXist, even if just temporarily.

Note that eXist will need to be able to write to the WEB-INF/exist-data directory, wherever Orbeon Forms .war file is uncompressed. So, especially if you're on UNIX, make sure that this directory is writable by the process running your app server.

#### License installation (Orbeon Forms PE only)

- If you are running Orbeon Forms CE, you don't need to install a license file.
- If you are running Orbeon Forms PE: 
  - complete the steps for your application server below
  - you can obtain a full licence from Orbeon, or get a trial license
  - before starting your servlet container, copy your license file under the Orbeon Forms WAR file as:
 
 ```
WEB-INF/resources/config/license.xml
```

With Orbeon Forms 4.1 and newer, you can also place license.xml file under the user's home directory. For example, on Unix systems:

 ```
~/.orbeon/license.xml
```

Orbeon Forms first searches for the license file within the WAR, and if not found attempts to find it under the home directory.

The benefit of this approach is that you don't have to find where the WAR file is deployed in your container, or to uncompress and recompress the WAR file with the license.

NOTE: Orbeon Forms uses Java's System.getProperty("user.home") to identify the user's home directory.\_\_ This corresponds to the user running the servlet container and not necessarily to the user of the developer or system administrator.

#### Base URL for internal services

This step is sometimes optional.

Depending on your setup, if things don't work out of the box (for example if you have database errors with the sample forms) you might have to set the oxf.url-rewriting.service.base-uri configuration property in your properties-local.xml file.

Often, it is enough to set it to the following (adjusting for port and prefix):

 ```
property
    as="xs:anyURI"
    name="oxf.url-rewriting.service.base-uri"
    value="http://localhost:8080/orbeon"/ 
```