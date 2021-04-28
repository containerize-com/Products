---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing on Linux

Download the latest release.

 ```
curl -sL -o monitoror $(curl -s https://api.github.com/repos/monitoror/monitoror/releases/latest | grep 'browser_download_url.*monitoror-linux-amd64' | cut -d: -f2,3 | tr -d \")
```

Make monitoror executable.

 ```
sudo chmod +x monitoror
```

Run monitoror.

 ```
./monitoror
```

You have installed successfully. Now, you can create configuration file for monitoring of services.

### Installation using Docker

 ```
docker run -p 8080:8080 monitoror/monitoror
```

#### **Explore**

You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [Top 5 Open Source Status Page Software for 2020](https://blog.containerize.com/2020/11/20/top-5-open-source-status-page-software-for-2020/)
 