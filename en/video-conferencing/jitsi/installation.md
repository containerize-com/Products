---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions using Docker**

First, run the following command to get the clone

 ```
 git clone https://github.com/jitsi/docker-jitsi-meet && cd docker-jitsi-meet
```

After a successful clone, Create a .env file by copying and adjusting env.example

 ```
 cp env.example .env
```

Now, set the password in the security section options of `.env` file by running the following bash script

 ```
 ./gen-passwords.sh<br></br>
```

Create required `CONFIG` directories

 ```
 mkdir -p ~/.jitsi-meet-cfg/{web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri}
```

In the last, run this command to spin the Docker image

 ```
 docker-compose up -d
```

Finally, you can access your application at this URL https://localhost:8443

#### **Explore**

You may find the following links relevant:

- **[Top 5 Open Source Video Conferencing Software of 2021](https://blog.containerize.com/2021/01/22/Top-5-Open-Source-Video-Conferencing-Software-of-2021/)**
- **[A Step By Step Guide To Set up Open Source Jitsi Meet](https://blog.containerize.com/2020/11/19/how-to-set-up-open-source-jitsi-meet/)**
- **[How Video Conferencing Software Can Benefit Your Business](https://blog.containerize.com/2020/11/13/how-video-conferencing-software-can-benefit-your-business/)**
 