---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once the pre-requisites are installed, run the following command to download the source files:

 ```
<pre data-title="Preformatted">```
git clone https://github.com/PostHog/posthog<br></br>
```
```

After that, run the following command to set up the database:

 ```
<pre data-title="Preformatted">```
docker-compose -f docker-compose.dev.yml up -d redis db
```
```

Then, go into the cloned directory and create and activate the virtual environment:

 ```
```
cd posthog<br data-rich-text-line-break="true"></br>python3 -m venv env<br data-rich-text-line-break="true"></br>source env/bin/activate
``` 
```

After that, run the following commands to install dependencies:

 ```
<pre data-title="Preformatted">```
pip install -r requirements.txt<br data-rich-text-line-break="true"></br>pip install -r requirements-dev.txt 
```
```

In the end, run the application with the following commands:

 ```
<pre data-title="Preformatted">```
DEBUG=1 python3 manage.py migrate<br data-rich-text-line-break="true"></br>DEBUG=1 ./bin/start
```
```

Finally, access the application in the browser at the following link.

 ```
<pre data-title="Preformatted">```
http://localhost<a data-rich-text-format-boundary="true" href="http://localhost:8000/">:</a>8000
```
```

#### **Explore**

<div class="entry-content">You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [How Free Business Analytics Tools Assist Your Business](https://blog.containerize.com/2021/03/12/how-free-business-analytics-tools-assist-your-business/)
 
 </div>