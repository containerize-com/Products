---
title: FAQs
onpagelink: faqs
weight: 4

---

### **FAQs**

### What is Modoboa used for?
Modoboa is an open source email server. That helps enterprises to setup their own open source email server for free.

### Is Modoboa free?
Modoboa is a self-hosted open source email server. And yes it is 100% free and open source.

### bower command is missing in manage.py
bower command is missing in `manage.py` if you don’t use the `--devel` option of the `modoboa-admin.py deploy` command.

To fix it, regenerate your instance or update your settings.py file manually. Look at devmode in https://github.com/tonioo/modoboa/blob/master/modoboa/core/commands/templates/settings.py.tpl

### Does Modoboa team helps you to install and maintain your email server?
If you don't have the knowledge to install your email server on your own? Modoboa team can assist you though they'll charge you for their services.
