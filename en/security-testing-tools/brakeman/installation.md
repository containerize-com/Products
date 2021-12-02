---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation**

#### **Install Brakeman On Ubuntu**

Brakeman source code scanner is simple and easy to get started software. Brakeman source code scanning tool can be installed as a Ruby gem or via Docker. Run the following using rubygems in project directory:

    gem install brakeman

If you want to install using Bundler, add the following to your Gemfile or gems.rb:

    gem "brakeman"

Then run bundler to install gems:

    bundle install

Run Brakeman static analysis software from the root of your Ruby on Rails application:

    cd path/to/your/app
    brakeman 

To fetch the latest build of Brakeman static code analysis using Docker run below:

    docker pull presidentbeef/brakeman

Now run Brakeman static analysis security from the root of your Ruby on Rails application:

    cd path/to/your/app
    docker run -v "$(pwd)":/code brakeman --color

For building from source you will need Git, Ruby, and RubyGems installed.

    git clone https://github.com/presidentbeef/brakeman.git
    cd brakeman
    gem build brakeman.gemspec
    gem install brakeman-*.gem

There are some scanning checks which are not run by default. Run below to run all checks:

    brakeman -A

Brakeman open source scan is run as a command line tool and it needs the root directory of the ruby on rails application to get started and to scan source code for vulnerabilities. Once Brakeman static code analysis is running and producing reports, it’s time to start fixing reported issues. After fixing an issue, run Brakeman once again.

Congratulations! You have now set up the Brakeman Tool static analysis tool. Enjoy!