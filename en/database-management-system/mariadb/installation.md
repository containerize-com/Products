---
title: Installation
onpagelink: installation
weight: 3

---

Installation
------------

Follow these steps to Install MariaDB on Ubuntu 18.04:

- To install MySQL, first update your local server’s package index by typing following command:
 
 ```
sudo apt update
```

- After updating process, now install it using the following command:
 
 ```
sudo apt install mariadb-server
```

- MariaDB service will start automatically but to check whether it is running, type:
 
 ```
sudo systemctl status mariadb
```

- To check version, type:
 
 ```
mysql -V
```