---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

 After setting up Python, run the following command to install virtualenv:  
 ```
<pre class="wp-block-preformatted">```
pip install virtualenv
```
```

Run the following command to create and activate a virtual environment:

 ```
python3.6 -m venv env source env/bin/activate
```

In case you’re using Windows, to activate the virtualenv you’ll need:

 ```
<pre class="wp-block-preformatted" id="block-b82d8c52-e9d3-4e44-87ff-451c9f14100c">```
env\Scripts\activate
```
```

Run the following command to update pip inside the virtual environment:

 ```
<pre class="wp-block-preformatted" id="block-7f95ab86-83bf-4983-ae18-16778a7e37b0">```
pip install <strong>--</strong>upgrade pip
```
```

Run the following command to install Django installer:

 ```
<pre class="wp-block-preformatted" id="block-a22ad9e6-3223-4b3b-bb02-4cd0155f08aa">```
pip install djangocms<strong>-</strong>installer
```
```

Now run the following commands to set up working directories:

 ```
<pre class="wp-block-preformatted" id="block-77c00386-35d0-4c0f-af67-529d185c2e76">```
mkdir tutorial<strong>-</strong>project
cd tutorial<strong>-</strong>project
```
```

Run the following command to setup Django project called mysite:

 ```
<pre class="wp-block-preformatted" id="block-dc3628b2-b848-445a-898b-995e0580a7de">```
djangocms mysite
```
```

Windows users may need to do a little extra to make sure Python files are associated correctly if that doesn’t work:

 ```
<pre class="wp-block-preformatted" id="block-dc3628b2-b848-445a-898b-995e0580a7de">```
assoc .py=Python.file ftype Python.File="C:\Users\Username\workspace\demo\env\Scripts\python.exe" "%1" %* 
```
```

The installer creates an admin user for you, with username/password `admin`/`admin`.

 ```
<pre class="wp-block-preformatted">```
python manage<strong>.</strong>py runserver
```
```

Access the site at [http://localhost:8000/](https://href.li/?http://localhost:8000/) in your browser.