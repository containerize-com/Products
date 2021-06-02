---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

To install the Mailu open-source mail server, you must first ensure that your system has a valid IP address and a fully qualified domain name. There should also be a valid MX record for the domain. To set server IP and hostname, run the below commands:

```
$ sudo hostnamectl set-hostname mail.example.com
```

Also add a server’s FQDN and IP address to /etc/hosts file.

```
$ sudo vi /etc/hosts
xxx.xxx.xxx.xxx mail.example.com
```

Once set, reboot the system

```
$ sudo reboot
```

The following ports should be allowed through your system firewall as they are critical for emails. You can open the ports with ufw as shown below:

```
$ sudo ufw allow proto tcp from any to any port
25,80,443,110,143,465,587,993,995
```

Before we proceed since Mailu is installed using the Docker and Docker Compose, so I’ll assume that you already have both setup. If not you can follow the official documentation for the setup:

- [How to Install Docker on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- [How to Install Docker Compose on Ubuntu](https://docs.docker.com/compose/install/)

After installing Docker and Docker Compose, proceed to create a directory where mailu will store its data:

```
$ sudo mkdir /mailu
```

Mailu uses a `docker-compose.yml` file and also relies on `mailu.env` for various settings. You need to generate a Mailu configuration for your environment using the online mailu setup utility. The generator will give you both a docker-compose.yml and a mailu.env file. Once the configuration is generated, you will receive links to use for downloading the files. Ensure that you download the files in the mailu directory. 

When done with the settings, run mailu with docker compose as below in mailu directory:

```
$ sudo docker-compose up -d
Recreating mailu_webdav_1    ... done 
Recreating mailu_fetchmail_1 ... done 
Recreating mailu_front_1     ... done 
Recreating mailu_antivirus_1 ... done 
Recreating mailu_admin_1     ... done 
Recreating mailu_antispam_1  ... done 
Recreating mailu_imap_1      ... done 
Recreating mailu_smtp_1      ... done 
Recreating mailu_webmail_1   ... done
```

Set admin user by running the below command:

```
$ docker-compose -p mailu exec admin flask mailu admin admin
example.com PASSWORD
Created admin user
```

### Explore

You may find the following links relevant:
- [Top 5 Open Source Mail Transfer Agents for Linux in 2020](https://blog.containerize.com/2020/10/02/top-5-open-source-mail-transfer-agents-for-linux-in-2020/)
- [Top 5 Open Source Newsletter Software in 2021](https://blog.containerize.com/2021/04/23/top-5-open-source-newsletter-software-in-2021/)