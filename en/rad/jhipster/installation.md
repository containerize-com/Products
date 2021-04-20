---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

After installing the above prerequisites, this [Docker](https://github.com/jhipster/generator-jhipster/blob/master/Dockerfile) file provides a Docker image.

For macOS, get the IP for DOCKER\_HOST by running the following command:

 ```
 docker-machine ip default
```

Now, run the following command to pull the development JHipster Docker image:

 ```
 docker pull jhipster/jhipster:master
```

After that, create a “jhipster” folder in your home directory:

 ```
 mkdir ~/jhipster<br></br>
```

So, run the Docker image with the following command:

 ```
docker run --name jhipster -v ~/jhipster:/home/jhipster/app -v ~/.m2:/home/jhipster/.m2 -p 8080:8080 -p 3000:3000 -p 3001:3001 -d -t jhipster/jhipster
```

Lastly, you can check your running container with the following command:

 ```
mkdir ~/jhipster
```

####  

#### **Explore**

You may find the following links relevant:

- **[ How to setup and create the first application with Jhipster](https://blog.containerize.com/2020/10/28/how-to-setup-and-create-the-first-application-with-jhipster/)**
- **[ How RAD Software Can Help You To Grow Business to Next Level](https://blog.containerize.com/2020/10/23/how-rad-software-can-help-you-to-grow-business-to-next-level/)**
 