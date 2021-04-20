---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

 **Install with GitHub**Clone the Let’s Chat repository, and install dependencies.

 ```
git clone https://github.com/sdelements/lets-chat.git
cd lets-chat
npm install

```

Optional — For custom settings, copy and edit settings.yml.sample:

 ```
cp settings.yml.sample settings.yml

```

Run Let’s Chat:

 ```
npm start

```

 **Install with Docker**If you'd like to be able to access the instance from the host without the container's IP, standard port mappings can be used:

 ```
docker run  --name some-letschat --link some-mongo:mongo -p 8080:8080 -d sdelements/lets-chat

```

Then, access it via http://localhost:8080 or http://host-ip:8080 in a browser.