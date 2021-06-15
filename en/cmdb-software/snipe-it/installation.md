---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### Installing using Docker

Once you have installed the pre-requisites, run the following command to pull the Docker image:

 ```
docker pull snipe/snipe-it
```

Next, create .env file named "my_env_file" and place the following data:

 ```
# Mysql Parameters MYSQL_ROOT_PASSWORD=YOUR_SUPER_SECRET_PASSWORD MYSQL_DATABASE=snipeit MYSQL_USER=snipeit MYSQL_PASSWORD=YOUR_snipeit_USER_PASSWORD # Email Parameters # - the hostname/IP address of your mailserver MAIL_PORT_587_TCP_ADDR=smtp.whatever.com #the port for the mailserver (probably 587, could be another) MAIL_PORT_587_TCP_PORT=587 # the default from address, and from name for emails MAIL_ENV_FROM_ADDR=youremail@yourdomain.com MAIL_ENV_FROM_NAME=Your Full Email Name # - pick 'tls' for SMTP-over-SSL, 'tcp' for unencrypted MAIL_ENV_ENCRYPTION=tcp # SMTP username and password MAIL_ENV_USERNAME=your_email_username MAIL_ENV_PASSWORD=your_email_password # Snipe-IT Settings APP_ENV=production APP_DEBUG=false APP_KEY=<<Fill in Later!>> APP_URL=http://127.0.0.1:YOUR_PORT_NUMBER APP_TIMEZONE=US/Pacific APP_LOCALE=en
```

Now, run the following command to run MySQL container:

 ```
docker run --name snipe-mysql --env-file=my_env_file --mount source=snipesql-vol,target=/var/lib/mysql -d -P mysql:5.6
```
Finally, you can spin the docker container with the following command: 

 ```
docker run --rm snipe/snipe-it 
```
