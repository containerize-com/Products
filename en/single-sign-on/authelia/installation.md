---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

Run the following command to clone the repo:

 ```
<pre class="wp-block-preformatted">```bash
git clone https://github.com/authelia/authelia.git
```
```

After successful clone, run the following commands:

 ```
<pre class="wp-block-preformatted">```bash
cd authelia/compose/local
```
```

 ```
<pre class="wp-block-preformatted" id="block-c9048714-c4d8-40c2-a7ce-9b4030a70bd4">```bash
sudo ./setup.sh
```
```

sudo is required to modify the /etc/hosts file.

Now, replace example.com with the domain you specified in the setup script and visit the url [https://secure.example.com](https://href.li/?https://secure.example.com).

### Running in Docker

Run the following command to clone the repo:

 ```
<pre class="wp-block-preformatted">```bash
git clone https://github.com/authelia/authelia.git
```
```

Run the following command after clone:

 ```
<pre class="wp-block-preformatted" id="block-49c15a5c-1fb3-4111-b2fd-586461decbc6">```bash
cd authelia/compose/lite
```
```

Modify the users\_database.yml the default username and password is Authelia

Modify the configuration.yml and docker-compose.yml with your respective domains and secrets

Finally, run the following command to spin up the Docker image:

 ```
<pre class="wp-block-preformatted" id="block-f555fde5-f21f-4ae0-9bd9-9f37e425b289">```bash
docker-compose up -d
```
```

####  

#### **Explore**

You may find the following links relevant:

- **[Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)**
 