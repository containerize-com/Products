---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Run the following command to clone the repo:

 ```
<pre class="wp-block-preformatted">```bash
git clone --recursive  https://github.com/OpenIdentityPlatform/OpenAM.git
```
```

After a successful clone run the following command:

 ```
<pre class="wp-block-preformatted">```bash
mvn install -f OpenAM
```
```

Add FQDN host name in /etc/hosts (Windows c:\\windows\\systems32\\drivers\\etc\\hosts):

 ```
<pre class="wp-block-preformatted">```bash
127.0.0.1 login.domain.com
```
```

Run OpenAM with the following command:

 ```
<pre class="wp-block-preformatted">```bash
mvn cargo:run -f OpenAM/openam-server
```
```

The next step is then to go to [http://login.domain.com:8080/openam](https://href.li/?http://login.domain.com:8080/openam) where you’ll see the OpenAM welcome page.

#### **Explore**

You may find the following links relevant:

- **[Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)**
 