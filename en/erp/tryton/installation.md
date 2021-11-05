---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

Pull docker image from hub.docker.com.

 ```
$ docker pull tryton/tryton
```

Start a PostgreSQL instance.

 ```
$ docker run --name tryton-postgres -e POSTGRES_PASSWORD=password_here -e POSTGRES_DB=tryton -d postgres
```

Setup the database.

 ```
$ docker run --link tryton-postgres:postgres -e DB_PASSWORD=password_here -it tryton/tryton trytond-admin -d tryton --all
```

Start a Tryton instance.

 ```
$ docker run --name tryton -p 8000:8000 --link tryton-postgres:postgres -e DB_PASSWORD=password_here -d tryton/tryton
```

After the successful installation, access the application by visiting http://localhost:8000.

