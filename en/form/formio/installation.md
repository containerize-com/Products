---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Install database Server, use the following command to install MongoDB

 ```
 sudo apt-get update; sudo apt install -y mongodb   MongoDB will be started automatically once installation is completed.
```

Once, the database server is installed, use the following command to install npm

 ```
 sudo apt-get install npm
```

Once, the database server is installed, use the following command to install Nodejs

 ```
 sudo apt-get install nodejs
```

Next, clone the repo using following command

 ```
 git clone <a href="https://github.com/formio/formio">https://github.com/formio/formio</a>

```

After clone is completed, use the following commands to run the server

 ```
 cd formio <br></br> sudo npm install<br></br> npm start 
```

When it is done, you will have a running Form.io management application running at the following address in your browser.

 ```
 <a href="https://github.com/formio/formio">http://</a>localhost:3001
```

Congrats You have successfullysetup Form.io

#### **Installation Instructions using Docker**

Docker images are located on docker hub, To pull it down, run the following docker command.

 ```
docker pull formio/formio-enterprise
```

Create a docker network to contain all the docker instances.

 ```
docker network create formio
```

Create the Mongo instance.

 ```
mkdir ~/opt/mongodb
# Double check permissions on /opt/mongodb
docker run -itd  \
  --name formio-mongo \
  --network formio \
  --volume ~/opt/mongodb:/data/db \
  --restart unless-stopped \
  mongo

```

Start the formio-enterprise instance.

 ```
docker run -itd \
  -e "ADMIN_EMAIL=<span id="cloak48020797f6318c36ba2d1b91ad9474af">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak48020797f6318c36ba2d1b91ad9474af').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy48020797f6318c36ba2d1b91ad9474af='&#97;dm&#105;n'+'&#64;';addy48020797f6318c36ba2d1b91ad9474af=addy48020797f6318c36ba2d1b91ad9474af+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text48020797f6318c36ba2d1b91ad9474af='&#97;dm&#105;n'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak48020797f6318c36ba2d1b91ad9474af').innerHTML+='<a '+path+'\''+prefix+':'+addy48020797f6318c36ba2d1b91ad9474af+'\'>'+addy_text48020797f6318c36ba2d1b91ad9474af+'<\/a>';</script>" \
  -e "ADMIN_PASS=CHANGEME" \
  -e "PRIMARY=true" \
  -e "LICENSE=YOURLICENSE" \
  -e "PORTAL_SECRET=CHANGEME" \
  -e "JWT_SECRET=CHANGEME" \
  -e "DB_SECRET=CHANGEME" \
  --restart unless-stopped \
  --name formio-server \
  --network formio \
  --link formio-mongo:mongo \
  --restart unless-stopped \
  -p 3000:80 \
  formio/formio-enterprise;
```