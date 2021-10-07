---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### Ubuntu Installation

Install Mattermost Server on a 64-bit machine.

Assume that the IP address of this server is 10.10.10.2.

**To install Mattermost Server on Ubuntu**

- Log in to the server that will host Mattermost Server and open a terminal window.
- Download the latest version of the Mattermost Server. In the following command, replace X.X.X with the version that you want to download:
 
 
 ```
wget https://releases.mattermost.com/X.X.X/mattermost-X.X.X-linux-amd64.tar.gz
```

- Extract the Mattermost Server files.
 
 
 ```
tar -xvzf mattermost*.gz
```

- Move the extracted file to the `/opt` directory.
 
 
 ```
sudo mv mattermost /opt
```

- Create the storage directory for files.
 
 
 ```
sudo mkdir /opt/mattermost/data
```

- Set up a system user and group called `mattermost` that will run this service, and set the ownership and permissions. 
  - Create the Mattermost user and group:
   
   
   ```
  sudo useradd --system --user-group mattermost
  ```
  
  
  - Set the user and group mattermost as the owner of the Mattermost files:
   
   
   ```
  sudo chown -R mattermost:mattermost /opt/mattermost
  ```
  
  
  - Give write permissions to the mattermost group:
   
   
   ```
  sudo chmod -R g+w /opt/mattermost
  ```
- Set up the database driver in the file /opt/mattermost/config/config.json
- Also set "SiteURL" to the full base URL of the site (e.g. "https://mattermost.example.com").
- Test the Mattermost server to make sure everything works.
- Setup Mattermost to use systemd for starting and stopping. 
  - Create a systemd unit file:
   
   
   ```
  sudo touch /lib/systemd/system/mattermost.service
  ```
  
  
  - Open the unit file as root in a text editor, and copy the following lines into the file:
   
   
   ```
  [Unit]
  Description=Mattermost
  After=network.target
  After=postgresql.service
  BindsTo=postgresql.service
  
  [Service]
  Type=notify
  ExecStart=/opt/mattermost/bin/mattermost
  TimeoutStartSec=3600
  Restart=always
  RestartSec=10
  WorkingDirectory=/opt/mattermost
  User=mattermost
  Group=mattermost
  LimitNOFILE=49152
  
  [Install]
  WantedBy=postgresql.service
  ```
  
  
  - Make systemd load the new unit.
   
   
   ```
  sudo systemctl daemon-reload
  ```
  
  
  - Check to make sure that the unit was loaded.
   
   
   ```
  sudo systemctl status mattermost.service
  ```
  
  
  - Start the service.
   
   
   ```
  sudo systemctl start mattermost.service
  ```
  
  
  - Verify that Mattermost is running.
   
   
   ```
  curl http://localhost:806
  ```
  
  
  - Set Mattermost to start on machine start up.
   
   
   ```
  sudo systemctl enable mattermost.service
  ```
 
#### Docker Installation

Deploy Mattermost using a multi-node configuration with Docker Compose. Experience with Docker Compose is recommended.

For a single-node preview of Mattermost (without email) see Local Machine Setup using Docker.

If you have any problems installing, see the troubleshooting guide. To submit an improvement or correction, click Edit at the top of this page.

Install Docker Compose using the online guide. You have to download the latest release from the Docker Compose Github page and put the binary on your /usr/local/bin folder. Usually, you can use the following command, replacing $dockerComposeVersion with the Docker Compose version to install:

 ```
sudo curl -L "https://github.com/docker/compose/releases/download/$dockerComposeVersion/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

##### Deploy the Mattermost Docker setup by running:

 ```
sudo apt-get install git
git clone https://github.com/mattermost/mattermost-docker.git
cd mattermost-docker
docker-compose build
mkdir -pv ./volumes/app/mattermost/{data,logs,config,plugins,client-plugins}
sudo chown -R 2000:2000 ./volumes/app/mattermost/
docker-compose up -d
```

The docker-compose network that is created defaults to 172.18.0.0/16. If you need to change the default network this link provides guidelines on how to do that. If the network is already set up with the default, you need to run the following command to remove it. Then, run the command again to regenerate the default network to include the new network setting.

 ```
docker network rm mattermost-server_mm-test
```

To verify the current Docker network use the following command to list it

 ```
docker network ls [OPTIONS]
```
