---
title: Installation
onpagelink: installation
weight: 3

---

### **Installation**

**Follow these instruction to install CUBRID on Ubuntu.**

- Install CUBRID using following apt-get command on Ubuntu.
 
 ```
$ sudo add-apt-repository ppa:cubrid/cubrid $ sudo apt-get update
```

- To install the latest version, execute following command.
 
 ```
$ sudo apt-get install cubrid
```

- Include version information in the command to install the earlier versions.
 
 ```
$ sudo apt-get install cubrid-8.4.3
```

- After installation is complete, configure environment variables including installation path of CUBRID and then apply them to system.
 
- Start Cubrid using following command.
 
 ```
cubrid service start
```

- Start or stop server process using following commands.
 
 ```
cubrid server start "dbname"
cubrid server stop "dbname"
```

- Test server connection.
 
 ```
csql -u dba demodb
```
