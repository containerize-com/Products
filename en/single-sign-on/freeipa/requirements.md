---
title: System Requirements
onpagelink: requirements
weight: 1

---

System Requirements
-------------------

Requirements to set up FreeIPA include:

- Linux/UNIX
- Git
 
<div class="col-lg-12">Features
--------

FreeIPA offers the following key features:

 </div><div class="col-lg-12">- Open Source
- Scalable
- Authentication / Authorization
- LDAP Support
- Secure
- Developer-Friendly
- Multiple UIs
- SSO
- Identity Provider
- Configurable
 
 </div><div class="col-lg-12">Installation Instructions
-------------------------

First, run the following command to clone the source code:

 ```
<pre class="wp-block-preformatted">```
git clone <a href="https://pagure.io/freeipa.git">https://pagure.io/freeipa.git</a>
```
```

Next, install the packages on your system by running the following commands:

 ```
<pre class="wp-block-preformatted">```
cd freeipa
cp freeipa.spec.in freeipa-builddep.spec 
sudo yum-builddep freeipa-builddep.spec
```
```

After that, run the following command:

 ```
<pre class="wp-block-preformatted">```
sudo dnf copr enable @freeipa/freeipa-master
```
```

Once all the dependencies are installed, run the following command to make build:

 ```
<pre class="wp-block-preformatted">```
./makerpms.sh
sudo yum localinstall dist/rpms/*.rpm
```
```

In addition, if you have IPA installed on your development system you can do some limited in-tree development of management plugins. To do this:

Server setup:

- As root user, install IPA using ipa-server-install
- Create ~/.ipa/alias/.pwd and enter the admin password
- Run kinit admin
- To run the server, execute python lite-server.py
 
Client setup:

- Copy /etc/ipa/default.conf into ~/.ipa/default.conf
- Replace xmlrpc\_uri with <http://127.0.0.1:8888/ipa/xml>
- To run the CLI, execute ./ipa &lt;command&gt;
 
Finally, FreeIPA will detect that it is running in-tree and will use the port and XML-RPC location that lite-server.py is listening only to. However, if you make changes to the server-side of a plugin you’ll need to restart lite-server.py.

#### **Explore**

You may find the following links relevant:

- **[Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)**
 
 </div>