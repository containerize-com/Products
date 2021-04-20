---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

These installation instructions are for macOS with Lion Server.

Firstly, edit the php.ini as mentioned below:

 ```
<pre class="wp-block-preformatted">```
short_open_tag = Onmax_execution_time = 60max_input_time = 90post_max_size = 30Mupload_max_filesize = 30MCheck:memory_limit = 128Mdisplay_errors = Offlog_errors = Onregister_globals = Offfile_uploads = On
```
```

Now, open the terminal and run the following commands:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="b9477ff9-86c8-423d-b788-a3bc27137e73" data-title="Preformatted" data-type="core/preformatted" id="block-b9477ff9-86c8-423d-b788-a3bc27137e73" spellcheck="false" tabindex="0">```
mysql -u root -p<br data-rich-text-line-break="true"></br>mysql> DROP DATABASE test;<br data-rich-text-line-break="true"></br>mysql> DELETE FROM mysql.user WHERE user = '';<br data-rich-text-line-break="true"></br>mysql> FLUSH PRIVILEGES;<br data-rich-text-line-break="true"></br>mysql>quit;
```
```

Create a plain text file named openemr.conf, insert the following data:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="8ffa0e28-b5ea-4b75-ae9c-67d3eca7be71" data-title="Preformatted" data-type="core/preformatted" id="block-8ffa0e28-b5ea-4b75-ae9c-67d3eca7be71" spellcheck="false" tabindex="0">```
<Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/documents><br data-rich-text-line-break="true"></br>order deny,allow<br data-rich-text-line-break="true"></br>Deny from all<br data-rich-text-line-break="true"></br></Directory><br data-rich-text-line-break="true"></br><Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/edi><br data-rich-text-line-break="true"></br>order deny,allow<br data-rich-text-line-break="true"></br>Deny from all<br data-rich-text-line-break="true"></br></Directory><br data-rich-text-line-break="true"></br><Directory /Library/Server/Web/Data/Sites/Default/openemr-4.1.0/sites/default/era><br data-rich-text-line-break="true"></br>order deny,allow<br data-rich-text-line-break="true"></br>Deny from all<br data-rich-text-line-break="true"></br></Directory>
```
```

After that, save it on the desktop and move it to /private/etc/apache2/sites in the terminal. y running the following command:

 ```
<pre class="block-editor-rich-text__editable wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text" contenteditable="true" data-block="435f0f8e-759e-418a-a20c-959b3f8b149d" data-title="Preformatted" data-type="core/preformatted" id="block-435f0f8e-759e-418a-a20c-959b3f8b149d" spellcheck="false" tabindex="0">```
sudo cp -p ~/Desktop/openemr.conf /etc/apache2/sites/openemr.conf
```
```

<div class="entry-content">Then, in the Finder: Go-&gt;Go to Folder-&gt;/Library/Server/Web/Data/Sites/Get Info for DefaultChange Sharing &amp; Permissions so all groups can Read &amp; Write, remember what it was to put it back later.Download, expand and move openemr-4.1.0 to /Library/Server/Web/Data/Sites/DefaultIn terminal:

 ```
cd /Library/Server/Web/Data/Sites/Default
ln -s openemr-4.1.0 openemr
cd openemr
sudo chmod 666 library/sqlconf.php
sudo chmod 666 interface/globals.php
sudo chown -R _www:_www sites
sudo chown -R _www:_www library/freeb
sudo chown -R _www:_www gacl/admin/templates_c
sudo chown -R _www:_www interface/main/calendar/modules/PostCalendar/pntemplates/cache
sudo chown -R _www:_www interface/main/calendar/modules/PostCalendar/pntemplates/compiled
```

Finally, open up web-browser and point it to the installation script at <http://localhost/openemr/setup.php>

#### **Explore**

You may find the following links relevant:

- [Automate Business Operations Using Free and Open Source Software](https://blog.containerize.com/2020/08/27/automate-business-operations-using-open-source-software/)
- [How Online Healthcare Software Empowers Healthcare Industry](https://blog.containerize.com/2021/02/12/how-online-healthcare-software-empowers-healthcare-industry/)
- [How To Set Up eHealth System Hospitalrun On Localhost](https://blog.containerize.com/2021/02/19/how-to-set-up-ehealth-system-hospitalrun-on-localhost/)
- [Features Exploration Of Medical Health Solution OpenEMR](https://blog.containerize.com/2021/02/26/features-exploration-of-medical-health-solution-openemr/)
 
 </div>