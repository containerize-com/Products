---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation

### Install WhatWeb On Ubuntu

WhatWeb scanner is simple and easy to get started software. To get started with WhatWeb, configure and setup environment with the necessary dependencies packages. whatweb is included in Kali Linux. You can also install it manually by running 'sudo apt install whatweb'. But here we will setup development environment usgin clone the WhatWeb repository:

    git clone https://github.com/urbanadventurer/WhatWeb.git
    cd WhatWeb/

This will install WhatWeb system wide under Linux or macOS:

    make install

Then run bundler the ruby dependency manager to install gems:

    gem install bundler

Next, update bundler:

    bundle update

Execute bundler from the WhatWeb source code folder to install dependencies defined in Gemfile:

    bundle install

WhatWeb should be installed in your local folder

    ./whatweb --version

Install Anemone as Spidering library:

    sudo gem install anemone

You can install rchardet for language character set detection to convert results to UTF-8:

    sudo gem install rchardet

Examples of how to use WhatWeb to scan www.google.com

    ./whatweb www.google.com

You can scan multiple websites by specifying the multiple URLs on the command line like:

    whatweb www.google.com slashdot.org twitter.com

Congratulations! You have now set up the WhatWeb Tool static analysis tool. Enjoy!