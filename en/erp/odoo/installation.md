---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation**

#### Installation using Github

First make sure you have installed all the dependencies. Then clone the latest Odoo repository into document root folder:

    git clone https://github.com/odoo/odoo.git
    cd odoo


Create a postgres user with a password using the pg admin gui:

*   Open pgAdmin.
*   Double-click the server to create a connection.
*   Select Object ‣ Create ‣ Login/Group Role.
*   Enter the username in the Role Name field (e.g. odoo).
*   Open the Definition tab and enter the password (e.g. odoo), then click Save.
*   Open the Privileges tab and switch Can login? to Yes and Create database? to Yes.

Navigate to the path of your Odoo Community installation (CommunityPath) and run pip on the requirements file in a terminal with Administrator privileges:

    spip install setuptools wheel
    pip install -r requirements.txt


Install rtlcss:

    npm install -g rtlcss

Once all dependencies are set up, Odoo can be launched by running odoo-bin. Common necessary configurations are:

*   PostgreSQL user and password.
*   Custom addon paths beyond the defaults, to load your own modules.

      
    
    
        python odoo-bin -r dbuser -w dbpassword –addons-path=addons -d mydb

Your Odoo web applications are ready to use.
