---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Element is based on `matrix-react-sdk` and `matrix-js-sdk` modules. Therefore, let's set them up first.

First, run the following command to clone and build matrix-js-sdk

    git clone https://github.com/matrix-org/matrix-js-sdk.git

After a successful clone, run the following commands

    pushd matrix-js-sdkyarn linkyarn installpopd

Similarly, run the following commands to set up matrix-react-sdk

    git clone https://github.com/matrix-org/matrix-react-sdk.gitpushd matrix-react-sdkyarn linkyarn link matrix-js-sdkyarn installpopd

Now, setup the Element application and run by running the following commands

    git clone https://github.com/vector-im/element-web.gitcd element-webyarn link matrix-js-sdkyarn link matrix-react-sdkyarn installyarn start

Finally, access this Video Messenger App at this URL [http://127.0.0.1:8080/](http://127.0.0.1:8080/)  into the browser.
