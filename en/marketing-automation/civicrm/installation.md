---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Instructions
-------------------------

### Installing CiviCRM for Joomla

#### Download and Un-tar CiviCRM Code

All CiviCRM code and packages used by CiviCRM (such as PEAR libraries) are included in the compressed CiviCRM distribution files ('tarballs'). Follow these steps to download and install the codebase:

- Download the appropriate tarball file from the [CiviCRM website](https://civicrm.org/download) within your browser. Tarball file-names include the CiviCRM version. For example, `civicrm-x.x.x-joomla.zip`. If you have command line access to your server, use `wget` and the URL of the file to pull a copy directly to your server. Then you can skip the next step.
- Upload this file to a folder in your root Joomla directory. Recommended location: `JOOMLA_ROOT/tmp/`.
- Unzip the package, which will create a directory called: `com_civicrm`. On cPanel, you can use the File Manager's Extract function to unzip the file you uploaded.
 
#### Run the Installer

- Login to your Joomla Administrator site.
- Go to Extensions &gt;&gt; Install/Uninstall.
- Use **Install from Directory** and enter the full path to the un-zipped com\_civicrm directory, which should be something like: `JOOMLA_ROOT/tmp/com_civicrm` . In most Joomla installations, the root directory and /tmp/ folder will already populate the "install from directory" field. You must simply add the /com\_civicrm/ subfolder at the end. Click Install. If that doesn't work: 
  - put the full file system path to the `com_civicrm`, something like `/home/yourusername/public_html/yourjoomladirname/tmp/com_civicrm/` - that worked for me on both a cPanel and a Virtualmin server.
- You should see "Component successfully installed" message.
 