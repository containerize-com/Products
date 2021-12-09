---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

### Install Metasploit On Ubuntu

Metasploit penetration testing software is simple and easy to get started software. Install and configure ruby on rails and postgresql dependencies packages for ubuntu pentesting tool. You should use the [Free Installer](https://github.com/rapid7/metasploit-framework/wiki/Nightly-Installers) which contains all of the dependencies and running with a few clicks but here we will setup source code development environment. Open a terminal on your system and set up Git, build tools and ruby dependencies:

    sudo apt update && sudo apt install -y git autoconf build-essential libpcap-dev libpq-dev zlib1g-dev libsqlite3-dev

Now login to Github and click the "Fork" button in the top-right corner of the metasploit open source repository. Create a git directory in your home folder and clone your fork to your local machine:

    export GITHUB_USERNAME=YOUR_USERNAME_FOR_GITHUB
    export GITHUB_EMAIL=YOUR_EMAIL_ADDRESS_FOR_GITHUB
    mkdir -p ~/git
    cd ~/git
    git clone git@github.com:$GITHUB_USERNAME/metasploit-framework
    cd ~/git/metasploit-framework

Create an upstream-master branch to track the Rapid7 remote repository receive updates:

    git remote add upstream git@github.com:rapid7/metasploit-framework.git
    git fetch upstream
    git checkout -b upstream-master --track upstream/master

Configure your your github account:

    git config --global user.name "$GITHUB_USERNAME"
    git config --global user.email "$GITHUB_EMAIL"
    git config --global github.user "$GITHUB_USERNAME"

Set up msftidy to run before each git commit and after each git merge to quickly identify potential issues:

    cd ~/git/metasploit-framework
    ln -sf ../../tools/dev/pre-commit-hook.rb .git/hooks/pre-commit
    ln -sf ../../tools/dev/pre-commit-hook.rb .git/hooks/post-merge

Run bundler to install gems in project directory:

    bundle install

Initialize the metasploit project hacking database:

    cd ~/git/metasploit-framework
    ./msfdb init

If the msfdb init command succeeds, then confirm that the database is accessible to metasploit framework ubuntu:

    ./msfconsole -qx "db_status; exit"

Congratulations! You have now set up the metasploit project and network intrusion detection system. Enjoy!

Explore
-------

In this article we discussed about Metasploit penetration testing framework and application security service. To learn about other open source security testing tools, please visit following page:

*   [Top Open Source Security Testing Tools](https://products.containerize.com/security-testing-tools/)
