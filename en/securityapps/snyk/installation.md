---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Install Snyk For Ruby

Snyk supports testing, monitoring and fixing Ruby projects in the CLI and Git integrations that have their dependencies managed by Bundler. Now please follow below step by step guide to set up Snyk. The Snyk utility CLI tool allows you to get started using the command line to install on npm run:

 ```
<pre class="command">```
npm install -g snyk
```
```

Once installed you will need to authenticate with your Snyk account:

 ```
<pre class="command">```
snyk auth
```
```

Test your local project with:

 ```
<pre class="command">```
snyk test
```
```

Get alerted for new vulnerabilities with:

 ```
<pre class="command">```
snyk monitor
```
```

Run below command to get a quick overview of all commands with more details and examples:

 ```
<pre class="command">```
snyk iac --help
```
```

Snyk is also provided as a set of Docker images that carry the runtime environment of each package manager. For example, the npm image will carry all of the needed setup to run npm install on the currently running container. Currently there are images for npm, Ruby, Maven, Gradle and SBT. The images can perform snyk test by default on the specified project which is mounted to the container as a read/write volume, and snyk monitor if the MONITOR environment variable is set when running the docker container. Please see the following RubyGems image example on how to run Snyk inside docker:

The host project folder will be mounted to /project on the container and will be used to read the dependencies file and write results for CI builds. Here's an example of running snyk test and snyk monitor in the image for RubyGems:

 ```
<pre class="command">```
docker run -it
    -e "SNYK_TOKEN="
    -e "USER_ID=1234"
    -e "MONITOR=true"
    -v ":/project"
  snyk/snyk-cli:rubygems test --org=my-org-name
```
```

The following Ruby on Rails manifest files are supported:

 ```
<pre class="command">```
Gemfile
Gemfile.lock
```
```

The following environment variables can be used when running the container on docker:

 ```
<pre class="command">```
SNYK_TOKEN
USER_ID
MONITOR
PROJECT_FOLDER
ENV_FLAGS
TARGET_FILE
```
```

To add projects, view vulnerability results for imported projects and then fix vulnerabilities via fix pull/merge requests, please check [Getting started with Snyk Open Source](https://support.snyk.io/hc/en-us/articles/360014875297-Getting-started-with-Snyk-Open-Source)

Congratulations! You have successfully installed Snyk CLI and build-time tool. Enjoy!

<div class="col-lg-12"><a class="anchor" id="explore" name="explore"></a>Explore
-------

In this article we discussed about Snyk open source security software. To learn about other open source security softwares, please visit following page:

- [Best Open Source Security Scanning Tools](https://products.containerize.com/securityapps/)
 
 </div>