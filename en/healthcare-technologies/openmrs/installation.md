---
title: Installation Guide
onpagelink: installation
weight: 3

---


#### **Installation Instructions**

Once pre-requisites are installed, run the following command to clone the source code:

    git clone https://github.com/openmrs/openmrs-core.git

Then, run the following commands:

    cd openmrs-coremvn clean package

This will generate the OpenMRS application in `webapp/target/openmrs.war` which you will have to deploy into an application server such as [tomcat](https://tomcat.apache.org/).

Now, you can simply deploy the `openmrs.war` into the application server jetty by running the following commands:

    cd openmrs-core/webappmvn jetty:run

Finally, you can access this health management information system at `localhost:8080/openmrs`.

