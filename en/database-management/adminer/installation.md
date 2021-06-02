---
title: Installation
onpagelink: installation
weight: 3

---

#### **Installation**

- Update system using following commands
 
 ```
sudo apt update
```

 ```
sudo apt upgrade
```

- Then install Adminer using command
 
 ```
sudo apt install adminer
```

- After that, activate Adminer app using command
 
 ```
sudo a2enconf adminer
```

- In the end, restart Apache
 
 ```
sudo systemctl reload apache2
```

- Then you can access Adminer from URL: <https://server-ip/adminer/>
 
![Adminer | Free Web Based Database Management System](/images/adminer_login.jpg "Adminer | Free Web Based Database Management System")