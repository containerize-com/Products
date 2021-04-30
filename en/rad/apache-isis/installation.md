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

