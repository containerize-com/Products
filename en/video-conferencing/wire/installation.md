---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once you have installed pre-requisites, run the following command to clone the source code.

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="cce66b9c-338d-4ad9-b8cd-8ec7b7b976f1" data-title="Preformatted" data-type="core/preformatted" id="block-cce66b9c-338d-4ad9-b8cd-8ec7b7b976f1" tabindex="0">```
git clone https://github.com/wireapp/wire-webapp.git
```
```

After a successful clone, run the following command

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="0941df23-2e55-42d5-886b-93d9cb3d1065" data-title="Preformatted" data-type="core/preformatted" id="block-0941df23-2e55-42d5-886b-93d9cb3d1065" spellcheck="false" tabindex="0">```
yarn
```
```

Then, rename `.env.localhost` to `.env`

After that, use a browser with disabled web security (`−−disable−web−security` in Chrome) to circumvent CORS issues when connecting to our backend from localhost

In the end, start the app with the following command

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="0941df23-2e55-42d5-886b-93d9cb3d1065" data-title="Preformatted" data-type="core/preformatted" id="block-0941df23-2e55-42d5-886b-93d9cb3d1065" spellcheck="false" tabindex="0">```
yarn start
```
```

Finally, access the app at this URL in the browser <https://localhost:8081/auth/>.

#### **Explore**

You may find the following links relevant:

- **[Top 5 Open Source Video Conferencing Software of 2021](https://blog.containerize.com/2021/01/22/Top-5-Open-Source-Video-Conferencing-Software-of-2021/)**
- **[A Step By Step Guide To Set up Open Source Jitsi Meet](https://blog.containerize.com/2020/11/19/how-to-set-up-open-source-jitsi-meet/)**
- **[How Video Conferencing Software Can Benefit Your Business](https://blog.containerize.com/2020/11/13/how-video-conferencing-software-can-benefit-your-business/)**
 