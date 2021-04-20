---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

First, run the following command to clone the openchain/docker repository from GitHub:

 ```
<pre class="wp-block-preformatted">```
git clone https://github.com/openchain/docker.git openchain
```
```

Second, run the following commands:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="ace783fa-9354-4d21-9dff-cc089ca68cdc" data-title="Preformatted" data-type="core/preformatted" id="block-ace783fa-9354-4d21-9dff-cc089ca68cdc" spellcheck="false" tabindex="0">```
cd openchain<br data-rich-text-line-break="true"></br>cp templates/docker-compose-direct.yml docker-compose.yml<br data-rich-text-line-break="true"></br>mkdir data<br data-rich-text-line-break="true"></br>cp templates/config.json data/config.json
```
```

Then, edit the configuration file (`data/config.json`):

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="50962945-5ea3-4393-aa62-1a08a091a010" data-title="Preformatted" data-type="core/preformatted" id="block-50962945-5ea3-4393-aa62-1a08a091a010" tabindex="0">```
nano data/config.json
```
```

Finally, set the `instance_seed` setting to a random (non-empty) string.

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
[...]<br data-rich-text-line-break="true"></br>   // Define transaction validation parameters<br data-rich-text-line-break="true"></br>   "validator_mode": {<br data-rich-text-line-break="true"></br>     // Required: A random string used to generate the chain namespace<br data-rich-text-line-break="true"></br>     "instance_seed": "",<br data-rich-text-line-break="true"></br>     "validator": {<br data-rich-text-line-break="true"></br> [...] 
```
```

In the end, run the following command to start the server:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="9eb15dfe-f483-43c0-b433-c09027c64395" data-title="Preformatted" data-type="core/preformatted" id="block-9eb15dfe-f483-43c0-b433-c09027c64395" spellcheck="false" tabindex="0">```
docker-compose up -d
```
```

####  

#### **Explore**

You may find the following links relevant:

- **[ A Beginners Guide To Setup Ethereum Node On Localhost](https://blog.containerize.com/2020/12/23/a-beginners-guide-to-setup-ethereum-node-on-localhost/)**
- **[ Top 5 Open Source Blockchain Platforms In 2020](https://blog.containerize.com/2020/12/11/top-5-open-source-blockchain-platforms-in-2020/)**
- **[ A Basic Guide on How To Create Ethereum Smart Contract](https://blog.containerize.com/2020/12/01/a-basic-guide-on-how-to-create-ethereum-smart-contract/)**
- **[How Blockchain Technology Can Upgrade Your Business Strategy](https://blog.containerize.com/2020/11/27/how-blockchain-technology-can-upgrade-your-business-strategy/)**
 