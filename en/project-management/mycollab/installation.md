---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Check Java requirements

You must need Java JRE 1.8 or higher to run MyCollab. Before you begin, you should check your current Java installation by using the following command:

 ```
java -version 
```

### Create the new MySQL Schema

Create the new MySQL schema with the following command

 ```
 CREATE SCHEMA `mycollab` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
 
```

### Download MyCollab

Go to https://mycollab.com/on-premise/ and select the appropriate MyCollab distribution for your organization. Download it and unzip on your local server, from now let’s call $MYCOLLAB\_HOME is the folder where you unzip MyCollab distribution.

### Install MyCollab on your server

Start MyCollab is different between Windows, and Unix.

**Windows**  Open the Windows Explorer, go to the folder $MYCOLLAB\_HOME/bin and click the bat file startup.bat

**Linux, MacOS**  Open the terminal, go to the folder $MYCOLLAB\_HOME/bin and run the script file startup.sh

The default port of running MyCollab is 8080. You are able to change the port by edit the value of the key server.port in the template configuration file $MYCOLLAB\_HOME/config/application.properties.ftl. After running the executable file startup.sh (on Linux / MacOS) or startup.bat (on Windows) then you open the browser with the address http://::