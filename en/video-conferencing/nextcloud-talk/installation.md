---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once pre-requisites are installed, run the following command to clone the source code:

 ```
 git clone https://github.com/nextcloud/server.git
```

Then, run the following commands:

 ```
cd /var/www<br></br>git submodule update --init<br></br>
```

If you prefer to install Nextcloud in a sub-folder, replace /var/www with /var/www/&lt;folder&gt;.

After that, create the data folder:

 ```
cd /var/www<br></br>mkdir data<br></br>
```

After that, run the following commands to adjust permissions:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="520eef20-84e0-4204-9327-f596e9a4a45e" data-title="Preformatted" data-type="core/preformatted" id="block-520eef20-84e0-4204-9327-f596e9a4a45e" spellcheck="false" tabindex="0">```
cd /var/www<br data-rich-text-line-break="true"></br>sudo chown -R www-data:www-data config data apps<br data-rich-text-line-break="true"></br>sudo chmod o-rw /var/www
```
```

Lastly, restart the Web serve:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected is-hovered rich-text" contenteditable="true" data-block="ec266582-a183-4af3-ae04-1ab35b8d58ac" data-title="Preformatted" data-type="core/preformatted" id="block-ec266582-a183-4af3-ae04-1ab35b8d58ac" tabindex="0">```
sudo systemctl restart httpd.service
```
```

Finally, access the application at http://localhost/.

#### **Explore**

You may find the following links relevant:

- **[Top 5 Open Source Video Conferencing Software of 2021](https://blog.containerize.com/2021/01/22/Top-5-Open-Source-Video-Conferencing-Software-of-2021/)**
- **[A Step By Step Guide To Set up Open Source Jitsi Meet](https://blog.containerize.com/2020/11/19/how-to-set-up-open-source-jitsi-meet/)**
- **[How Video Conferencing Software Can Benefit Your Business](https://blog.containerize.com/2020/11/13/how-video-conferencing-software-can-benefit-your-business/)**
 