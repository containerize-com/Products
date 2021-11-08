---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

### Install Apache Mesos on Linux

For Linux operating system setup, please follow the below installions steps to install Apache Mesos multi cluster management installation setup. Run all the below commands but first update the packages by running:

    sudo apt-get update

Next, install tar wget git tools:

    sudo apt-get install -y tar wget git

Install the latest OpenJDK with:

    sudo apt-get install -y openjdk-8-jdk

Install autotools using:

    sudo apt-get install -y autoconf libtool

Now, install other Mesos dependency packages:

    sudo apt-get -y install build-essential python-dev python-six python-virtualenv libcurl4-nss-dev libsasl2-dev libsasl2-modules maven libapr1-dev libsvn-dev zlib1g-dev iputils-ping

There are different ways you can get Apache Mesos. Store these files in the /usr/share folder, which is available to all users. Download and unzip the latest stable release of Apache Mesos installation files:

    cd /usr/share/
    sudo mkdir mesos
    sudo wget https://downloads.apache.org/mesos/1.11.0/mesos-1.11.0.tar.gz
    sudo tar -zxf mesos-1.11.0.tar.gz
    cd /usr/share/mesos/mesos--1.11.0

Next, build the software using commands:

    sudo mkdir build
    cd build
    ../configure
    sudo make

Run and Install test suite with:

    sudo make check
    sudo make install

To run Mesos, first start the Mesos Master. Change into the build directory and start Mesos master:

    cd build 
    ./bin/mesos-master.sh –ip=127.0.0.1 –work_dir=/var/lib/mesos 

After starting the master, start the slave.

    ./bin/mesos-slave.sh –master=127.0.0.1:5050 –work_dir=/tmp/mesos

If facing permissions issues then run:

    ./bin/mesos-slave.sh –master=127.0.0.1:5050 –work_dir=/tmp/mesos –no-systemd_enable_support

Now Mesos is running. To monitor it please visit the Mesos in browser with:

    localhost:5050

To test your Apache Mesos installation, you can configure it with cluster computing framework, Apache Spark. Congratulations! You have successfully setup Apache Mesos on Linux. Enjoy!
