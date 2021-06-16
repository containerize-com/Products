---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

### Install BeEF On Ubuntu

BeEF kali linux framework is simple and easy to get started software. Install and configure BeEF dependency packages. Now login to Github and click the "Fork" button in the top-right corner of the beef repository and clone your fork to your local machine:

    git clone https://github.com/beefproject/beef beef
    cd ~/beef

Bundler is essential for tracking and installing the missing gems in ruby application. Run bundler to install gems in project directory:

    gem install bundler

Next, run the install script in the BeEF directory:

    ./install

This script installs the required operating system packages and all the prerequisite Ruby gems.

BeEF uses YAML files in order to configure the core functionality and the extensions. Most of the core BeEF configurations are in the main config.yaml configuration file in the BeEF directory. Modify the config.yaml files located in the extension folder to configure extensions.

To start BeEF, simply run:

    ./beef


It's best to regularly update BeEF to the latest version. If you're using BeEF from the GitHub repository, updating by:

    git pull

The default login credentials for BeEF are beef / beef . The credentials can be changed in the configuration file config.yaml

Congratulations! You have now set up the BeEF xss framework. Enjoy!
