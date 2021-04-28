---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

First, you need root permissions that can be done with the following command

 ```
 sudo su
```

Then run the following command

 ```
 cd /opt
```

Now run the following command to download the files and will show a message with basic instructions

 ```
 curl https://s3-eu-west-1.amazonaws.com/aws.openvidu.io/install_openvidu_latest.sh | bash<br></br>
```

OpenVidu Platform configuration is specified in the **`.env`** file with environment variables. You must give a value to properties **`DOMAIN_OR_PUBLIC_IP`** and **`OPENVIDU_SECRET`**. Default empty values will fail. Therefore, you can change the **`CERTIFICATE_TYPE`** if you have a valid domain name. Setting this property to `letsencrypt` will automatically generate a valid certificate for you (it is required to set property `LETSENCRYPT_EMAIL`). Or if for any unknown reason you prefer to use your own certificate, set the property to `owncert` and place the certificate files as explained.

By default, the OpenVidu Call application comes with OpenVidu Platform. It is accessible in the URL

 ```
 https://DOMAIN_OR_PUBLIC_IP:HTTPS_PORT/
```

Now, run the application with the following command

 ```
 ./openvidu start
```

Finally, application will be available at https://DOMAIN\_OR\_PUBLIC\_IP/

#### **Explore**

You may find the following links relevant:

- **[Top 5 Open Source Video Conferencing Software of 2021](https://blog.containerize.com/2021/01/22/Top-5-Open-Source-Video-Conferencing-Software-of-2021/)**
- **[A Step By Step Guide To Set up Open Source Jitsi Meet](https://blog.containerize.com/2020/11/19/how-to-set-up-open-source-jitsi-meet/)**
- **[How Video Conferencing Software Can Benefit Your Business](https://blog.containerize.com/2020/11/13/how-video-conferencing-software-can-benefit-your-business/)**
 