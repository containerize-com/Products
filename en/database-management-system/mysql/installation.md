---
title: Installation
onpagelink: installation
weight: 3

---

Installation
------------

Follow these steps to Install MySQL on Ubuntu 18.04:

- To install MySQL, first update your local server’s package index by typing following command:
 
 ```
sudo apt update
```

- Then install the MySQL default package using the following command:
 
 ```
sudo apt install mysql-server
```

- For secure installation type following command:
 
 ```
sudo mysql_secure_installation
```

- MySQL will automatically started after completion of installation process. Then check MySQL server is running or not using this command:
 
 ```
sudo systemctl status mysql
```

- To log into the MySQL server as the root user type following command:
 
 ```
sudo mysql
```

- MySQL shell can be exit using following command:
 
 ```
exit
```