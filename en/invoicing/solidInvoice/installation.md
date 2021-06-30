---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

#### Installing using Docker

Pull the container with the following command.

 ```
docker pull solidinvoice/solidinvoice:latest 
```

Use the command below to run the container.

 ```
docker run -d -p 8080:80 solidinvoice/solidinvoice
```

Now, open your browser and type http://Server_IP_OR_DOMAIN to access the SolidInvoice.

This docker image does not come with a database. SolidInvoice needs a MySQL server. Use the command below to link SolidInvoice to external database container.

 ```
docker run -d --name solidinvoice --link db:db solidinvoice/solidinvoice
```

### Installing using Git

Clone the repository using the following command.

 ```
$ git clone https://github.com/SolidInvoice/SolidInvoice.git
```

Navigate to repository directory and install all the dependencies.

 ```
$ cd SolidInvoice
$ php composer.phar install
```

Finally, install the Node packages and dump all the web assets.

 ```
$ npm install
$ ./node_modules/.bin/gulp
```

### Installing using Composer

Run the following command to install SolidInvoice via composer.

 ```
$ php composer.phar create-project solidinvoice/solidinvoice
```

Install the Node packages and dump all the web assets

 ```
$ npm install
$ ./node_modules/.bin/gulp
```

Now, you need to create virtual host file at Nginx or Apache web server and point it the installation directory.

