---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

After installing the above prerequisites, run the following command

 ```
 curl https://codeload.github.com/apache/isis-app-simpleapp/zip/2.0.0-M4 | jar xv
```

Once command is successful, go into the generated directory

 ```
 cd isis-app-simpleapp-2.0.0-M4
```

Now, run this command

 ```
 mvn clean install<br></br>
```

Finally, following command will compile and run the app

 ```
mvn -pl webapp spring-boot:run
```

Access the application into the browser at this URL http://localhost:8080.

#### **Explore**

You may find the following links relevant:

- **[ How to setup and create the first application with Jhipster](https://blog.containerize.com/2020/10/28/how-to-setup-and-create-the-first-application-with-jhipster/)**
- **[ How RAD Software Can Help You To Grow Business to Next Level](https://blog.containerize.com/2020/10/23/how-rad-software-can-help-you-to-grow-business-to-next-level/)**
 