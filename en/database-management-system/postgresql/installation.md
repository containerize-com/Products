---
title: Installation
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Follow these steps to Install PostgreSQL on Ubuntu 18.04:

- To install PostgreSQL, first refresh your server’s local package index:
 
 ```
sudo apt update
```

- Then, install the Postgres package along with a -contrib package that adds some additional utilities and functionality:
 
 ```
sudo apt install postgresql postgresql-contrib
```

- During installation, a user account postgres is created. Switch over to the postgres account on your server by typing:
 
 ```
sudo -i -u postgres
```

- Then you can access the Postgres prompt by typing:
 
 ```
psql
```

- To exit out of the PostgreSQL prompt, run the following:
 
 ```
\q
```

- To return to your regular system user, run the following exit command:
 
 ```
exit
```

- If you are logged in as the postgres account, you can create a new role by running following command:
 
 ```
createuser --interactive
```

- Now create the database with following createdb command:
 
 ```
createdb firstdb
```

- Then open a Postgres Prompt with the New Role
 
 ```
sudo adduser firstuser
```

- Once this new account is available, you can connect to the database by typing:
 
 ```
sudo -u sammy psql
```

- Finally check your current connection information by typing following command:
 
 ```
\conninfo
```

- It should give following output:
 
 ```
You are connected to database "firstdb" as user "firstuser" via socket in "/var/run/postgresql" at port "5432".
```