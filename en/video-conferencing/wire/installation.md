---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Once you have installed pre-requisites, run the following command to clone the source code.

    git clone https://github.com/wireapp/wire-webapp.git

After a successful clone, run the following command

    yarn

Then, rename `.env.localhost` to `.env` 

After that, use a browser with disabled web security (`−−disable−web−security` in Chrome) to circumvent CORS issues when connecting to our backend from localhost

In the end, start the app with the following command

    yarn start

Finally, access the app at this URL in the browser [https://localhost:8081/auth/](https://localhost:8081/auth/).

