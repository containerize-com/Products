---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Download Caddy from GiHub.

Then Use curl command

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">curl -OL "https://github.com/caddyserver/caddy/releases/latest/download/ASSET"</span>
```
```

You can also download using using wget command

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">wget "https://github.com/caddyserver/caddy/releases/latest/download/ASSET"</span>
```
```

Note\*: Replace \[ASSET\] with the filename for your platform.

Run following commands to install on Debian, Ubuntu, Raspbian

 ```
<pre class="wp-block-code">```
<span class="hljs-attr">echo "deb [trusted=yes] https://apt.fury.io/caddy/ /" \
    | sudo tee -a /etc/apt/sources.list.d/caddy-fury.list
sudo apt update</span>
```
```

After installation, Caddy will start automatically.