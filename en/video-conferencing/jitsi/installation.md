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

