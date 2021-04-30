---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing ERPNext on Ubuntu 18.04

Update and Upgrade APT.

 ```

sudo apt-get update 
sudo apt-get upgrade

```

Install ERPNext dependencies by running the below command.

 ```
sudo apt install libffi-dev python-pip python-dev libssl-dev wkhtmltopdf curl git
```

Install Node Js and Redis by using the following commands.

 ```

sudo curl --silent --location https://deb.nodesource.com/setup_8.x | sudo bash -
sudo apt-get install gcc g++ make
sudo apt-get install -y nodejs redis-server
sudo npm install -g yarn

```

Install Nginx.

 ```
sudo apt-get install nginx
```

Run below command to install MariaDB.

 ```
sudo apt-get install mariadb-server mariadb-client
```

Run the commands below to secure MariaDB server. Answer the questions when prompted.

 ```
sudo mysql_secure_installation
```

Connect to MariaDB server.

 ```
sudo mysql -u root -p
```

Create a database with name erpnext.

 ```
CREATE DATABASE erpnext;
```

Create a database user called erpnextuser. Replace password\_here with your own password.

 ```
CREATE USER 'erpnextuser'@'localhost' IDENTIFIED BY 'password_here';
```

Grant the user full access to the database.

 ```

GRANT ALL ON erpnext.* TO 'erpnextuser'@'localhost' IDENTIFIED BY 'password_here' WITH GRANT OPTION;

```

Save changes and exit.

 ```

FLUSH PRIVILEGES;
exit;

```

Create directory for project.

 ```
sudo mkdir /var/www/html/erpnext
```

Install and configure ERPNext by running the following commands.

 ```

cd /var/www/html/erpnext
git clone https://github.com/frappe/bench bench-repo
sudo pip install -e bench-repo
bench init erpnext && cd erpnext

```

Create a new site for project. Replace example.com with actual domain name.

 ```

bench new-site example.com
bench start

```

Open your browser and visit site.

 ```
http://example.com:8000
```

Follow the wizard for ERPNext installation.

