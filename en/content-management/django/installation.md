---
title: Installation Guide
onpagelink: installation
weight: 3

---
### **Installation**

After setting up Python, run the following command to install virtualenv:  

    pip install virtualenv

Run the following command to create and activate a virtual environment:

    python3.6 -m venv env source env/bin/activate

In case you’re using Windows, to activate the virtualenv you’ll need:

    env\Scripts\activate

Run the following command to update pip inside the virtual environment:

    pip install --upgrade pip

Run the following command to install Django installer:

    pip install djangocms-installer

Now run the following commands to set up working directories:

    mkdir tutorial-project
    cd tutorial-project

Run the following command to setup Django project called mysite:

    djangocms mysite

Windows users may need to do a little extra to make sure Python files are associated correctly if that doesn’t work:

    assoc .py=Python.file ftype Python.File="C:\Users\Username\workspace\demo\env\Scripts\python.exe" "%1" %* 

The installer creates an admin user for you, with username/password `admin`/`admin`.

    python manage.py runserver

Access the site at [http://localhost:8000/](https://href.li/?http://localhost:8000/) in your browser.
