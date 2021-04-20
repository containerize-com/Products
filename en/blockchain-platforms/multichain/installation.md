---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

First, for Ubuntu, install the dependencies by running the following commands:

 ```
<pre class="wp-block-preformatted">```
sudo apt-get update<br></br>sudo apt-get install -y software-properties-common<br></br>sudo apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev git python python-pip<br></br>sudo add-apt-repository ppa:bitcoin/bitcoin<br></br>sudo apt-get install -y libdb4.8-dev libdb4.8++-dev<br></br>sudo pip install pathlib2<br></br>
```
```

Then, run the following command to clone the source code.

 ```
<pre class="wp-block-preformatted">```
git clone https://github.com/MultiChain/multichain.git
```
```

After that, run the following commands to make a build:

 ```
<pre class="wp-block-preformatted">```
cd multichain<br></br>set MULTICHAIN_HOME=$(pwd)<br></br>mkdir v8build<br></br>cd v8build
```
```

However, you can use pre-built headers and binaries of Google’s V8 JavaScript engine by downloading and expanding [linux-v8.tar.gz](https://github.com/MultiChain/multichain-binaries/raw/master/linux-v8.tar.gz) in the current directory.

Finally, run the following commands to compile:

 ```
<pre class="wp-block-preformatted">```
cd $MULTICHAIN_HOME<br></br>./autogen.sh<br></br>./configure<br></br>make
```
```

####  

#### **Explore**

You may find the following links relevant:

- **[ A Beginners Guide To Setup Ethereum Node On Localhost](https://blog.containerize.com/2020/12/23/a-beginners-guide-to-setup-ethereum-node-on-localhost/)**
- **[ Top 5 Open Source Blockchain Platforms In 2020](https://blog.containerize.com/2020/12/11/top-5-open-source-blockchain-platforms-in-2020/)**
- **[ A Basic Guide on How To Create Ethereum Smart Contract](https://blog.containerize.com/2020/12/01/a-basic-guide-on-how-to-create-ethereum-smart-contract/)**
- **[How Blockchain Technology Can Upgrade Your Business Strategy](https://blog.containerize.com/2020/11/27/how-blockchain-technology-can-upgrade-your-business-strategy/)**
 