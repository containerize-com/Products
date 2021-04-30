---
title: Installation Guide
onpagelink: installation
weight: 3

---


#### **Installation Instructions**

Once you have installed the pre-requisites, the first next step is to Install Samples, Binaries, and Docker Images.

Secondly, For macOS, you will need to use a location under /Users, /Volumes, /private, or /tmp. Get into the directory into which you will install the Fabric Samples and binaries by running the following command:

    curl -sSL https://bit.ly/2ysbOFE | bash -s

Thirdly, run the following command to set PATH environment variable:

    export PATH=<path to download location>/bin:$PATH

In addition, the script will download the Hyperledger Fabric docker images from [Docker Hub](https://hub.docker.com/u/hyperledger/) into your local Docker registry and tag them as ‘latest’.

Now, run the following command:

    cd fabric-samples/test-network

In this directory, you will find an annotated script, `network.sh`, that stands up a Fabric network using the Docker images on your local machine.

After that, from inside the `test-network` directory, run the following command to remove any containers or artifacts from any previous runs:

    ./network.sh down

Finally, run the following command to bring up the network:

    ./network.sh up

