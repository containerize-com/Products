---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Guide for Live Helper Chat**

#### Install from command line

Copy install-cli.php script to root folder (lhc\_web if you pulled from github)

 ```
 cp cli/install-cli.php install-cli.php
 
```

Copy default example.settings.ini to settings.ini. Don't forget to modify them.

 ```
cp cli/example.settings.ini cli/settings.ini

```

Install Live Helper Chat

 ```
 php install-cli.php cli/settings.ini
 
```
