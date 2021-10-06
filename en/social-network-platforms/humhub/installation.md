---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

Once all the pre-requisites are installed, run the following command to create the database. 

 ```
 CREATE DATABASE humhub CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Then, run the following command to clone the git repository into the htdocs directory of your webserver:

 ```
git clone https://github.com/humhub/humhub.git
```

Now, navigate to your HumHub web-root directory and fetch your composer dependencies by running the following command:

 ```
composer install
```

Finally, you can access the HumHub web installer on this address into the browser:

 ```
http://localhost/humhub.
```

