---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

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

