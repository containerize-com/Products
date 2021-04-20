---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Step 1: Download Craft

Craft can be downloaded with Composer or by manually downloading a zip or tar.gz archive. The end result will be the same, so go with whichever route you feel more comfortable with.

### Step 2: Set the File Permissions

For Craft to run properly, PHP needs to be able to write to the following places:

- .env
- composer.json
- composer.lock
- config/license.key
- config/project/\*
- storage/\*
- vendor/\*
- web/cpresources/\*
 
The exact permissions you should be setting depends on the relationship between the system user that PHP is running as, and who owns the actual folders/files.

- If they are the same user, use `744`.
- If they’re in the same group, then use `774`.
- If you’re not sure and like to live life on the edge, use `777`.
 
### Step 3: Set a Security Key

Each Craft project should have a unique security key, which is shared between each of the environments that the project is installed on.

You can generate and assign the key manually, or have Craft do it for you with a terminal command.

#### Set the Key Manually

First generate a cryptographically secure key, preferably using a password generator like 1Password. (There’s no length limit.)

Then open up your `.env` file (you may need to use an app like Transmit (opens new window)to do this if you’re running macOS), and find this line:

 ```
SECURITY_KEY=""
```

Paste your security key inside the quotes and save the file.

#### Set the Key from Your Terminal

In your terminal, go to your project’s root directory and run the following command:

 ```
php craft setup/security-key
```

### \#Step 4: Create a Database

Next up, you need to create a database for your Craft project. Craft 3 supports both MySQL 5.5+ and PostgreSQL 9.5+.

If you’re given a choice, we recommend the following database settings in most cases:

- MySQL 
  - Default Character Set: `utf8`
  - Default Collation: `utf8_unicode_ci`
- PostgreSQL 
  - Character Set: `utf8`
 
### \#Step 5: Set up the Web Server

Create a new web server to host your Craft project. Its document root (or “webroot”) should point to your web/ directory (or whatever you’ve renamed it to).

If you’re not using MAMP (opens new window)or another localhosting tool, you will probably need to update your hosts file, so your computer knows to route requests to your chosen host name to the local computer.

- macOS/Linux/Unix: `/etc/hosts`
- Windows: `\Windows\System32\drivers\etc\hosts`
 
You can test whether you set everything up correctly by pointing your web browser to `http:///index.php?p=admin/install` (substituting with your web server’s host name). If Craft’s Setup Wizard is shown, the host name is correctly resolving to your Craft installation.

### \#Step 6: Run the Setup Wizard

Finally, it’s time to run Craft’s Setup Wizard. You can either run that from your terminal or your web browser.

#### Terminal Setup

In your terminal, go to your project’s root directory and run the following command to kick off the Setup Wizard:

 ```
php craft setup
```

The command will ask you a few questions to learn how to connect to your database, and then kick off Craft’s installer. Once it’s done, you should be able to access your new Craft site from your web browser.

#### Web Browser Setup

In your web browser, go to `http:///index.php?p=admin/install` (substituting with your web server’s host name). If you’ve done everything right so far, you should be greeted by Craft’s Setup Wizard.

The first step of the installer is to accept the license agreement (opens new window). Scroll down through the agreement (reading it all, of course) and click the “Got it” button to accept.

The second step is to enter your database connection information.

The third step of the installer is to create an admin account. Don’t be one of those people and be sure to pick a strong password.

The final step is to define your System Name, Base URL, and Language.

Click “Finish up” to complete the setup process. A few seconds later, you should have a working Craft install!

If it was successful, Craft will redirect your browser to the control panel.

Congratulations, you’ve just installed Craft!

Now build something incredible.