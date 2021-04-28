---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once the pre-requisites are installed, run the following command to download the source files:

 ```
<pre data-title="Preformatted">```
git clone https://github.com/plausible/hosting<br></br>
```
```

<span style="font-size: 12.16px;">After that, run the following command:</span>

 ```
<pre data-title="Preformatted">```
cd hosting
```
```

In the downloaded directory you'll find two important files:`docker-compose.yml` - installs and orchestrates networking between your Plausible server, Postgres database, Clickhouse database (for stats), and an SMTP server. It comes with sensible defaults that are ready to go, although you're free to tweak the settings if you wish.

`plausible-conf.env` - configures the Plausible server itself. Full configuration options are documented [here](https://plausible.io/docs/self-hosting-configuration).

After that, the configuration file has placeholders for the required parameters. Firstly, add your admin credentials in `plausible-conf.env`. Secondly, generate a random 64-character secret key which will be used to secure the app. Here's a simple way to generate one:

 ```
<pre data-title="Preformatted">```
openssl rand -base64 64
```
```

Now, run the server with the following command:

 ```
<pre data-title="Preformatted">```
docker-compose up --detach
```
```

Finally, you can access this business intelligence reporting software into the browser at the following address:

 ```
<pre data-title="Preformatted">```
http://{hostname}:8000
```
```

#### **Explore**

<div class="entry-content">You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [How Free Business Analytics Tools Assist Your Business](https://blog.containerize.com/2021/03/12/how-free-business-analytics-tools-assist-your-business/)
 
 </div>