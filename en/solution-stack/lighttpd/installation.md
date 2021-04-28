---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Installing on Ubuntu**

Install Lighttpd web server using following command

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">$ sudo apt install lighttpd</span>
```
```

To test installation, go to your website or IP address

![Secure, Flexible And Lightweight Web Server](/images/Lighttpd_-_Check_status_on_browser.png "Secure, Flexible And Lightweight Web Server")

#### **Installing from source**

Download a release from www.lighttpd.net/download.

Use following commands to install via git

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">git clone https://git.lighttpd.net/lighttpd/lighttpd1.4.git
cd lighttpd1.4
./autogen.sh
</span>
```
```

Use these commands if you want to install via svn

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">svn checkout https://github.com/lighttpd/lighttpd1.4/trunk lighttpd1.4</span>
```
```

Fetch updates

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">svn update</span>
```
```

To install dependencies, run this command

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">apt-get build-dep lighttpd</span>
```
```

Configure

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">./configure --help</span>
```
```

Build using make command

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">make</span>
```
```

After a successful build, now install the package

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">su make install</span>
```
```