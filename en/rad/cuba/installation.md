---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

First clone the repo using the following command:

 ```
 git clone <a href="https://href.li/?https://github.com/cuba-platform/cuba.git">https://github.com/cuba-platform/cuba.git</a>
```

After that, Your directory should look like this after cloning CUBA Gradle Plugin and CUBA:

 ```
```
 Work/<br></br>   cuba/<br></br>   cuba-gradle-plugin/   
``` 
```

Now, open the terminal and run the following commands to build and install the plugin into your local Maven repository:

 ```
 cd work<br></br> cd cuba-gradle-plugin/<br></br> gradlew install<br></br>
```

After that, run these commands:

 ```
 cd ../cuba<br></br> gradlew install
```

So now, For using snapshot version, edit the **`build.gradle`** file by changing the `ext.cubaVersion` property and add `mavenLocal()` to the `repositories` section

In the last, build and deploy your application by running the following command:

 ```
 gradlew deploy
```

####  

#### **Explore**

You may find the following links relevant:

- **[ How to setup and create the first application with Jhipster](https://blog.containerize.com/2020/10/28/how-to-setup-and-create-the-first-application-with-jhipster/)**
- **[ How RAD Software Can Help You To Grow Business to Next Level](https://blog.containerize.com/2020/10/23/how-rad-software-can-help-you-to-grow-business-to-next-level/)**
 