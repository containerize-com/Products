---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Once pre-requisites are installed, download the source code from this [**link**](https://builds.matomo.org/matomo.zip).

After that, unzip the folder and open your FTP client and upload the Matomo files in ‘binary mode’ to the desired location on your web server.

If you have SSH access to your server, you can use it instead of FTP as it is much faster:

    run wget https://builds.matomo.org/matomo.zip && unzip matomo.zip

Now, open your web browser and navigate to the URL to which you uploaded Matomo, setup the database by following the instructions given [here](https://matomo.org/faq/how-to-install/faq_23484/) and complete the installation process.

Finally, access the application by opening the URL into the browser.

    e.g. http://yourdomain.org/analytics/ 
