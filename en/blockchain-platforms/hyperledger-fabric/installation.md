---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once you have installed the pre-requisites, the first next step is to Install Samples, Binaries, and Docker Images.

Secondly, For macOS, you will need to use a location under /Users, /Volumes, /private, or /tmp. Get into the directory into which you will install the Fabric Samples and binaries by running the following command:

 ```
<pre class="wp-block-preformatted">```
curl <strong>-</strong>sSL https:<strong>//</strong>bit<strong>.</strong>ly<strong>/</strong>2ysbOFE <strong>|</strong> bash <strong>-</strong>s
```
```

Thirdly, run the following command to set PATH environment variable:

 ```
<pre class="wp-block-preformatted">```
export PATH=<path to download location>/bin:$PATH
```
```

In addition, the script will download the Hyperledger Fabric docker images from [Docker Hub](https://hub.docker.com/u/hyperledger/) into your local Docker registry and tag them as ‘latest’.

Now, run the following command:

 ```
<pre class="wp-block-preformatted">```
cd fabric<strong>-</strong>samples<strong>/</strong>test<strong>-</strong>network
```
```

In this directory, you will find an annotated script, `network.sh`, that stands up a Fabric network using the Docker images on your local machine.

After that, from inside the `test-network` directory, run the following command to remove any containers or artifacts from any previous runs:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="f4ee55e2-fbd8-44b4-a850-7bff9bb0e968" data-title="Preformatted" data-type="core/preformatted" id="block-f4ee55e2-fbd8-44b4-a850-7bff9bb0e968" spellcheck="false" tabindex="0">```
./network.sh down
```
```

Finally, run the following command to bring up the network:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="2229fbca-fd75-4a6b-9e23-bcb5f05f1f7f" data-title="Preformatted" data-type="core/preformatted" id="block-2229fbca-fd75-4a6b-9e23-bcb5f05f1f7f" tabindex="0">```
./network.sh up
```
```

####  

#### **Explore**

You may find the following links relevant:

- **[ A Beginners Guide To Setup Ethereum Node On Localhost](https://blog.containerize.com/2020/12/23/a-beginners-guide-to-setup-ethereum-node-on-localhost/)**
- **[ Top 5 Open Source Blockchain Platforms In 2020](https://blog.containerize.com/2020/12/11/top-5-open-source-blockchain-platforms-in-2020/)**
- **[ A Basic Guide on How To Create Ethereum Smart Contract](https://blog.containerize.com/2020/12/01/a-basic-guide-on-how-to-create-ethereum-smart-contract/)**
- **[How Blockchain Technology Can Upgrade Your Business Strategy](https://blog.containerize.com/2020/11/27/how-blockchain-technology-can-upgrade-your-business-strategy/)**
 