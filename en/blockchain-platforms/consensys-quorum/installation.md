---
title: Installation Guide
onpagelink: installation
weight: 3

---




#### **Installation Instructions**

Once pre-requisites are installed, run the following command to clone the source code:

    git clone https://github.com/ConsenSys/quorum.git

After that, run the following commands to install dependencies:

    cd quorum-masteryarn install

Now, run the following command to automatically build on changes to any files in the src directory:

    yarn start

Finally, run the following command to start the application:

    node build/index.js

