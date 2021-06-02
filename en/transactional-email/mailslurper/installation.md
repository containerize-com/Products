---
title: Installation Guide
onpagelink: installation
weight: 3

---
### Installation

To begin first you must [download](https://github.com/mailslurper/mailslurper/releases) the version of MailSlurper for your operating system. If you are on a Mac running OSX you will need to download the file named mailslurper-x.x-osx.zip. If you are going to run MailSlurper on Windows download the file named mailslurper-x.x-windows.zip.

The next step is to extract the contents somewhere and review the configuration file `config.json`. For this example let's say you are going to run MailSlurper on your local machine. There are three addresses and ports that need to be configured.

- Web application address and port
- Services address and port
- SMTP server address and port

Let's see what that might look like if we wanted to access the web-based administrator using http://localhost:8080, with services running on port 8888 and the SMTP server running on port 25. Configurations will look like following.

```
{
	"wwwAddress": "localhost",
	"wwwPort": 8080,
	"serviceAddress": "localhost",
	"servicePort": 8085,
	"smtpAddress": "localhost",
	"smtpPort": 2500,
	"dbEngine": "SQLite",
	"dbHost": "",
	"dbPort": 0,
	"dbDatabase": "./mailslurper.db",
	"dbUserName": "",
	"dbPassword": "",
	"maxWorkers": 1000,
	"autoStartBrowser": false,
	"keyFile": "",
	"certFile": "",
	"adminKeyFile": "",
	"adminCertFile": "",
	"authenticationScheme": "",
	"authSecret": "",
	"authSalt": "",
	"authTimeoutInMinutes": 120,
	"credentials": {}
}
```


### Explore

You may find the following links relevant:
- [Top 5 Open Source Mail Transfer Agents for Linux in 2020](https://blog.containerize.com/2020/10/02/top-5-open-source-mail-transfer-agents-for-linux-in-2020/)
- [Top 5 Open Source Newsletter Software in 2021](https://blog.containerize.com/2021/04/23/top-5-open-source-newsletter-software-in-2021/)