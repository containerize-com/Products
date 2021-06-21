---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

First clone the repo using the following command:

     git clone https://github.com/cuba-platform/cuba.git

After that, Your directory should look like this after cloning CUBA Gradle Plugin and CUBA:

     Work/   cuba/   cuba-gradle-plugin/   

Now, open the terminal and run the following commands to build and install the plugin into your local Maven repository:

     cd work cd cuba-gradle-plugin/ gradlew install

After that, run these commands:

     cd ../cuba gradlew install

So now, For using snapshot version, edit the **`build.gradle`** file by changing the `ext.cubaVersion` property and add `mavenLocal()` to the `repositories` section

In the last, build and deploy your application by running the following command:

     gradlew deploy

