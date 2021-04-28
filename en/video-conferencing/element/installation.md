---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Element is based on `matrix-react-sdk` and `matrix-js-sdk` modules. Therefore, let's set them up first.

First, run the following command to clone and build matrix-js-sdk

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="cce66b9c-338d-4ad9-b8cd-8ec7b7b976f1" data-title="Preformatted" data-type="core/preformatted" id="block-cce66b9c-338d-4ad9-b8cd-8ec7b7b976f1" tabindex="0">```
git clone https://github.com/matrix-org/matrix-js-sdk.git
```
```

After a successful clone, run the following commands

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="0941df23-2e55-42d5-886b-93d9cb3d1065" data-title="Preformatted" data-type="core/preformatted" id="block-0941df23-2e55-42d5-886b-93d9cb3d1065" spellcheck="false" tabindex="0">```
pushd matrix-js-sdk<br data-rich-text-line-break="true"></br>yarn link<br data-rich-text-line-break="true"></br>yarn install<br data-rich-text-line-break="true"></br>popd
```
```

Similarly, run the following commands to set up matrix-react-sdk

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="fa8ec0e9-fcf8-45c1-9257-a89877e2908b" data-title="Preformatted" data-type="core/preformatted" id="block-fa8ec0e9-fcf8-45c1-9257-a89877e2908b" spellcheck="false" tabindex="0">```
git clone https://github.com/matrix-org/matrix-react-sdk.git<br data-rich-text-line-break="true"></br>pushd matrix-react-sdk<br data-rich-text-line-break="true"></br>yarn link<br data-rich-text-line-break="true"></br>yarn link matrix-js-sdk<br data-rich-text-line-break="true"></br>yarn install<br data-rich-text-line-break="true"></br>popd
```
```

Now, setup the Element application and run by running the following commands

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="38ff9876-b68c-43f0-8f0d-866a7abe710c" data-title="Preformatted" data-type="core/preformatted" id="block-38ff9876-b68c-43f0-8f0d-866a7abe710c" spellcheck="false" tabindex="0">```
git clone https://github.com/vector-im/element-web.git<br data-rich-text-line-break="true"></br>cd element-web<br data-rich-text-line-break="true"></br>yarn link matrix-js-sdk<br data-rich-text-line-break="true"></br>yarn link matrix-react-sdk<br data-rich-text-line-break="true"></br>yarn install<br data-rich-text-line-break="true"></br>yarn start
```
```

Finally, access this Video Messenger App at this URL <http://127.0.0.1:8080/> into the browser.

#### **Explore**

You may find the following links relevant:

- **[Top 5 Open Source Video Conferencing Software of 2021](https://blog.containerize.com/2021/01/22/Top-5-Open-Source-Video-Conferencing-Software-of-2021/)**
- **[A Step By Step Guide To Set up Open Source Jitsi Meet](https://blog.containerize.com/2020/11/19/how-to-set-up-open-source-jitsi-meet/)**
- **[How Video Conferencing Software Can Benefit Your Business](https://blog.containerize.com/2020/11/13/how-video-conferencing-software-can-benefit-your-business/)**
 