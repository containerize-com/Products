---
title: Installation
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Follow these steps to Install Apache Tomcat 9 on Ubuntu 18.04:

- First of all, update the package index using following command:
 
 ```
sudo apt update
```

- Install the OpenJDK package by running following command:
 
 ```
sudo apt install default-jdk
```

- After that, create Tomcat User.
 
 ```
sudo useradd -r -m -U -d /opt/tomcat -s /bin/false tomcat
```

- Now, download the Tomcat archive in the /tmp directory using the following wget command:
 
 ```
wget http://www-eu.apache.org/dist/tomcat/tomcat-9/v9.0.27/bin/apache-tomcat-9.0.27.tar.gz -P /tmp
```

- Extract the Tomcat archive and move it to the /opt/tomcat directory using following command:
 
 ```
sudo tar xf /tmp/apache-tomcat-9*.tar.gz -C /opt/tomcat
```

- After that, create the symbolic link called ‘latest’ that points to the Tomcat installation directory:
 
 ```
sudo ln -s /opt/tomcat/apache-tomcat-9.0.27 /opt/tomcat/latest
```

- Use following command to change the directory ownership:
 
 ```
sudo chown -RH tomcat: /opt/tomcat/latest
```

- Then set executable flag for the scripts inside bin directory.
 
 ```
sudo sh -c 'chmod +x /opt/tomcat/latest/bin/*.sh'
```

- To run Tomcat as a service you need to create a new unit file.
- Create a file named tomcat.service in the /etc/systemd/system/:
 
 ```
sudo nano /etc/systemd/system/tomcat.service
```

- Paste the following configuration into newly created file:
 
 ```
[Unit]
Description=Tomcat 9 servlet container
After=network.target

[Service]
Type=forking

User=tomcat
Group=tomcat

Environment="JAVA_HOME=/usr/lib/jvm/default-java"
Environment="JAVA_OPTS=-Djava.security.egd=file:///dev/urandom -Djava.awt.headless=true"

Environment="CATALINA_BASE=/opt/tomcat/latest"
Environment="CATALINA_HOME=/opt/tomcat/latest"
Environment="CATALINA_PID=/opt/tomcat/latest/temp/tomcat.pid"
Environment="CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC"

ExecStart=/opt/tomcat/latest/bin/startup.sh
ExecStop=/opt/tomcat/latest/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
```

- Note\*: Modify the value of JAVA\_HOME according to the path to your Java installation.
- Save and close the file and restart using following command:
 
 ```
sudo systemctl daemon-reload
```

- Start Tomcat Service using following command
 
 ```
sudo systemctl start tomcat
```

- Check status with the following command:
 
 ```
sudo systemctl status tomcat
```

- Now If there are no errors, enable the Tomcat service.
 
 ```
sudo systemctl enable tomcat
```

- After that, adjust the Firewall.
 
 ```
sudo ufw allow 8080/tcp
```

- Then configure Tomcat Web Management Interface.
 
 ```
sudo nano /opt/tomcat/latest/conf/tomcat-users.xml
```

- Edit the following two files to allow access to the web interface from anywhere.
- Comment out the lines under tag.
- For the Host Manager app, open the following file:
 
 ```
sudo nano /opt/tomcat/latest/webapps/manager/META-INF/context.xml
```

- For the Manager app, open the following file:
 
 ```
sudo nano /opt/tomcat/latest/webapps/host-manager/META-INF/context.xml
```

- After that, comment out the code as follows:
 
 `<Context antiResourceLocking="false" privileged="true" >`