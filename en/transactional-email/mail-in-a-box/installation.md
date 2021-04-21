---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

SSH into your new VPS. Use the IP address that you took note of earlier.

 ```
$ ssh <span id="cloaka4f93424eca46d7662dcbc069e04d0e2">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloaka4f93424eca46d7662dcbc069e04d0e2').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addya4f93424eca46d7662dcbc069e04d0e2='r&#111;&#111;t'+'&#64;';addya4f93424eca46d7662dcbc069e04d0e2=addya4f93424eca46d7662dcbc069e04d0e2+'203'+'&#46;'+'0'+'&#46;'+'113';var addy_texta4f93424eca46d7662dcbc069e04d0e2='r&#111;&#111;t'+'&#64;'+'203'+'&#46;'+'0'+'&#46;'+'113';document.getElementById('cloaka4f93424eca46d7662dcbc069e04d0e2').innerHTML+='<a '+path+'\''+prefix+':'+addya4f93424eca46d7662dcbc069e04d0e2+'\'>'+addy_texta4f93424eca46d7662dcbc069e04d0e2+'<\/a>';</script>.0
```

Your root user password can be found in the Vultr control panel, in the Overview section.

Copy and paste the following into your terminal.

 ```
$ curl -s https://mailinabox.email/setup.sh | sudo bash
```

Several Ubuntu packages will now be installed for you. Eventually, you'll be asked a few installation questions:

- Your email address This will default to something like <span id="cloak72fb41072db45cd32c9bc696829496ef">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak72fb41072db45cd32c9bc696829496ef').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy72fb41072db45cd32c9bc696829496ef='m&#101;'+'&#64;';addy72fb41072db45cd32c9bc696829496ef=addy72fb41072db45cd32c9bc696829496ef+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text72fb41072db45cd32c9bc696829496ef='m&#101;'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak72fb41072db45cd32c9bc696829496ef').innerHTML+='<a '+path+'\''+prefix+':'+addy72fb41072db45cd32c9bc696829496ef+'\'>'+addy_text72fb41072db45cd32c9bc696829496ef+'<\/a>';</script>. Change that to whatever you prefer.
- Hostname This should default to the hostname that you have already set up for your VPS, for example box.example.com. Leave this as-is.
- Configuring tzdata Select your timezone.
- Password Finally, you'll be asked to enter a new password. This will be used for your new email account, as well as logging into the admin interface.
 
Once installation is complete, you'll be presented with a success message, and a website link to the admin interface.

 ```
Your Mail-in-a-Box is running.

Please log in to the control panel for further instructions at:

https://203.0.113.0/admin

You will be alerted that the website has an invalid certificate. Check that
the certificate fingerprint matches:

C0:9B:FF:04:2B:2D:8F:47:5A:BF:82:E9:F2:2A:E8:CB:51:F3:12:88:48:6B:9E:72:7C:33:8B:D5:88:B7:05:D3:4B:6C:22:80:5F
```