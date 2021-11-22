---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

### Install OpenShift on Linux

Below installation instructions assume that all the depency packages of the OpenShift are installed and up to date on your Ubuntu system. For Ubuntu setup, please follow the below installions steps to install OpenShift on ubuntu. A single node installation will run OKD services in docker containers. Docker Engine runtime is required on for the installation system. So, first import Docker GPG key:

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Now, add Docker APT repository to your Ubuntu system:

    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

The Docker repository is now added, run the commands below to update, install and verify Docker CE on Ubuntu:

    sudo apt update && sudo apt -y install docker-ce
    docker version

Next, add your User account to docker group.

    sudo usermod -aG docker $USER

At this point, Docker is successfully installed. Download the OpenShift Origin client utility on Ubuntu from Git Hub repository:

    wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz

Uncompress downloaded tar file, move to created folder, then copy kubectl and oc binaries to the /usr/local/bin directory:

    tar xvf openshift-origin-client-tools*.tar.gz
    cd openshift-origin-client*/
    sudo mv  oc kubectl  /usr/local/bin/

Verify installation of Red Hat container platform OpenShift client utility by command:

    oc version

Allow use of Insecure Docker registry and restart Docker service after adding the file in terminal:

    cat << EOF | sudo tee /etc/docker/daemon.json 
     {
         "insecure-registries" : [ "172.30.0.0/16" ]
     }
    EOF

    sudo systemctl restart docker

Next, start OKD server on local interface – 127.0.0.1:8443 by running the following command:

    oc cluster up

Openshift Origin command option help:

    oc cluster up --help

To login as administrator account, use command:

    oc login -u system:admin

Change to the default project:

    oc project default

Deploy OKD cluster integrated container image registry using command:

    oc adm registry

You can check current project status:

    oc status

Now you can access OpenShift admin console in a browser with credentials Username: developer, Password: developer. Browse to 127.0.0.1:8443 to access OpenShift web console. You can change host IP in OCP configuration file. A Project can be created from the web console by login into Openshift cluster.

Congratulations! You have successfully setup OpenShift Origin on Ubuntu. Enjoy!