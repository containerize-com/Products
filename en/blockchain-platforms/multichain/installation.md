---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

First, for Ubuntu, install the dependencies by running the following commands:

    sudo apt-get updatesudo apt-get install -y software-properties-commonsudo apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev git python python-pipsudo add-apt-repository ppa:bitcoin/bitcoinsudo apt-get install -y libdb4.8-dev libdb4.8++-devsudo pip install pathlib2

Then, run the following command to clone the source code.

    git clone https://github.com/MultiChain/multichain.git

After that, run the following commands to make a build:

    cd multichainset MULTICHAIN_HOME=$(pwd)mkdir v8buildcd v8build

However, you can use pre-built headers and binaries of Google’s V8 JavaScript engine by downloading and expanding [linux-v8.tar.gz](https://github.com/MultiChain/multichain-binaries/raw/master/linux-v8.tar.gz) in the current directory.

Finally, run the following commands to compile:

    cd $MULTICHAIN_HOME./autogen.sh./configuremake

