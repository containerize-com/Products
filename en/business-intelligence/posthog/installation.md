---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation Instructions**

Once the pre-requisites are installed, run the following command to download the source files:

    git clone https://github.com/PostHog/posthog

After that, run the following command to set up the database:

    docker-compose -f docker-compose.dev.yml up -d redis db

Then, go into the cloned directory and create and activate the virtual environment:

    cd posthogpython3 -m venv envsource env/bin/activate

After that, run the following commands to install dependencies:  

    pip install -r requirements.txtpip install -r requirements-dev.txt 

In the end, run the application with the following commands:

    DEBUG=1 python3 manage.py migrateDEBUG=1 ./bin/start

Finally, access the application in the browser at the following link.

    http://localhost:8000

