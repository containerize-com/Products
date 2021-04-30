---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Download Caddy from GiHub.

Then Use curl command

    curl -OL "https://github.com/caddyserver/caddy/releases/latest/download/ASSET"

You can also download using using wget command

    wget "https://github.com/caddyserver/caddy/releases/latest/download/ASSET"

Note\*: Replace \[ASSET\] with the filename for your platform.

Run following commands to install on Debian, Ubuntu, Raspbian

    echo "deb [trusted=yes] https://apt.fury.io/caddy/ /" \
        | sudo tee -a /etc/apt/sources.list.d/caddy-fury.list
    sudo apt update

After installation, Caddy will start automatically.

