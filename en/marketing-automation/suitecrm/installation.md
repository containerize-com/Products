---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installation using Github

First make sure you have installed all the dependencies. Then clone the latest SuiteCRM repository into document root folder:

 ```
<pre class="command">```
git clone https://github.com/salesagility/SuiteCRM.git
sudo mv SuiteCRM suitecrm
 ```
```

Set appropriate permissions for suitecrm directory:

```
<pre class="command">```
sudo chown -R www-data:www-data suitecrm 
sudo chmod -R 755 suitecrm 
ls -ld suitecrm

```
```

Now open your web browser and type the URL below to access the SuiteCRM web installer wizard. http://SERVER\_IP/suitecrm/install.php OR http://localhost/suitecrm/install.php

Follow the installation wizard steps. Your SuiteCRM website is ready.