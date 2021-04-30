---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Before setting up the development environment, you first need to setup a BigBlueButton 2.2 server that can be found at this [link](https://docs.bigbluebutton.org/2.2/install.html)

First, run the following command:

 ```
 sudo apt-get install wget
```

Now, run the command to install core development tools

 ```
 sudo apt-get install git-core ant ant-contrib openjdk-8-jdk-headless
```

With the JDK installed, you need to set the JAVA\_HOME variable. Edit `~/.profile`

 ```
 vi ~/.profile<br></br>
```

Add the following line at the end of the file

 ```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
```

Reload your profile (this will happen automatically when you next login, but we’ll do it explicitly here to load the new environment variable).

 ```
source ~/.profile
```

Do a quick test to ensure JAVA\_HOME is set.

 ```
echo $JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
```

In the next step, you need to install a number of tools using sdkman.

 ```
curl -s “https://get.sdkman.io” | bash<br></br>source “$HOME/.sdkman/bin/sdkman-init.sh”<br></br>sdk install gradle 5.5.1<br></br>sdk install grails 3.3.9<br></br>sdk install sbt 1.2.8<br></br>sdk install maven 3.5.0<br></br>
```

For setting up the code, Fork the BigBlueButton repository into your GitHub account and then clone it.

Run the following command to add the remote repository to our local clone.

 ```
git remote add upstream https://github.com/bigbluebutton/bigbluebutton.git<br></br>
```

Then, run the following commands to fetch the most up to date version of the remote repository.

 ```
git fetch upstream
```

After that, create a new branch to start your work and base the `v2.2.x-release` release branch

 ```
git checkout -b my-changes-branch upstream/v2.2.x-release
```

After setting up the server, we will setup the front end. Run the following commands to install Meteor.js

 ```
cd ~/dev/bigbluebutton/bigbluebutton-html5<br data-rich-text-line-break="true"></br>curl https://install.meteor.com/ | sh
```

Next, there is one change required to settings.yml to get webcam and screen share working in the client (assuming you’re using HTTPS already). The first step is to find the value for `kurento.wsUrl` packaged settings.yml.

 ```
grep "wsUrl" /usr/share/meteor/bundle/programs/server/assets/app/config/settings.yml
```

Next, edit the development settings.yml and change `wsUrl` to match what was retrieved before.

 ```
vi private/config/settings.yml
```

You’re now ready to run the HTML5 code. First shut down the packaged version of the HTML5 client so you are not running two copies in parallel.

 ```
sudo systemctl stop bbb-html5
```

Finally, install the npm dependencies and run the front end with the following commands:

 ```
meteor npm install<br></br>npm start<br></br>
```

####  

