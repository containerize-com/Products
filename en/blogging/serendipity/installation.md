---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Guide
------------------

### Uploading Serendipity 

You can install Serendipity into either your document root of the web server, or into any subdirectory you like. Make sure that you upload ALL files that you extracted from your Serendipity release .ZIP or .TGZ file, including empty directories. Make sure, your FTP editor doesn’t report any trouble or permission errors when uploading Serendipity files.

### Permissions on files/directories

Very important to Serendipity are the directories archives, templates\_c and uploads. The directory archives is used to store pregenerated files, the directory templates\_c will contain automatically compiled HTML templates from the Smarty Templating Engine and the directory uploads will contain any media files you upload to your Blog. This means, all three folders will require write access for your webserver.

PHP usually runs as a specific user that is different from the FTP user account you use to upload files. So, if your FTP user is able to upload files, this does not necessarily mean, that the PHP process will be able to access the same files/directory. Depending on your webservers setup, you might need to change the permissions (CHMOD) of the three mentioned directory to something like 777 (read, write and execute permissions for everyone, meaning “world writable”), 775 (meaning read, write and execute permissions for the owner and the group of the files/directory, but not “everybody”). Which one to use is very specific to your webserver’s setup. Please ask your provider, if you are unsure which permissions you need to use!

On top of those three directories, Serendipity will also need to write the two files .htaccess and serendipity\_config\_local.inc.php into the root of the Serendipity installation. That means that also the directory where you upload the full Serendipity installation into needs to have permissions that allow the PHP server to create those two files - so remember to also set your top directory (like “serendipity” or “blog”) to 777 or 775. You can reset those permissions on the core directory after the installation to something like 744 again, because once the mentioned files are written, Serendipity only needs to alter those files.

If you plan to use the SPARTACUS plugin to download plugins and templates over the web, PHP also needs to be able to write to the directories plugins and templates.

### Installing

Once you have uploaded Serendipity to your web space you can call the installer interface via something like http://example.org/serendipity/index.php. It will take no longer than 1-2 minutes to install Serendipity.

On this screen, you will see a basic pre-installation report that shows you a diagnosis of your Web Server settings. All variables that possibly might create trouble are listed orange-coloured. You usually do not need to pay attention to those, unless you are experiencing errors. Here’s an example screenshot:

Fatal problems are shown in red color. The most usual case of a red error is if Serendipity cannot create the directories templates\_c, archives or uploads. In this case, please follow the suggestions in the “Permissions on Files/Directories” step of this documentation.

On the bottom of the diagnosis screen, you can choose if you want to perform a “Simple installation” or the “Expert installation”. Both methods actually perform the same steps; however the “Simple installation” only shows you very few initial configuration options so that you can install Serendipity quickly. The “Expert installation” will ask you to enter every configuration directive.

Since the goal of this Document is to show how fast you can install Serendipity, we will only discuss the “Simple installation” right now, so please click on this link and you will see a screen like this:

### Database Settings

In this section, you must enter the credentials to access the selected database. First you choose the database type you want to use for Serendipity. Serendipity will only show the database types that are available to PHP. Note, that your provider must have given you credentials to access your database, and that this database must already exist. Serendipity requires an empty database, so if you have not yet created a database, just do that via the SQL command “CREATE DATABASE serendipity” using your favourite SQL tool (phpMyAdmin, phpPgAdmin, sqliteAdmin).

Now you just fill in the values you got from your provider for the host, user, password and database name fields.

### General Settings

This section contains the most basic Blog setup options. First you enter the username and password for your Admin user. It is recommended to not use special characters like Umlauts for the username. Your username will not be displayed in the blog to enhance login security - to display your username, the “real name” option will be used.

The E-Mail address of your admin user is very important, since you will receive trackback and comment notification emails to that address.

The blog name and description will later be shown on the frontpage of your blog. Of course, all those settings can later be changed!

As the last option of this section, you need to choose the language of your blog. Note that this will be the default language for both your frontend of the blog and the personal language of your editor. All other users you are later able to create can define their own language for viewing your blog!

### Complete installation

After you have entered all options, you click on the button “Complete installation”. Serendipity will then try to connect to your database. If that fails, it will inform you of this.

Also, Serendipity will perform checks and create directories, so it might ask you to create some more directories/permissions as discussed above.

If you ever have troubles because of wrong auto-detected directories or URLs, you might need to call the “Expert installation” wizard. This gives you several additional configuration options to indicate the used directories, database table prefixes etc. Note well that the Expert Installation will show you the path layout as it currently is configured; if you change the path/URL locations there, you need to enter values that reflect your ACTUAL layout, and not the layout you would want. If you want to install Serendipity into a different directory than displayed, you need to move the files via FTP/SSH there.

Else, Serendipity will create the required database tables and sets up your blog as configured:

REMEMBER WELL that if you ever want to reinstall Serendipity from scratch, you need to DROP all Serendipity-created Database tables. Else, reinstalling into the same database will Serendipity lead to think that it shall not re-create the tables and authors. This would then lead to duplicate inserted plugins and non-matching user credentials you entered!
