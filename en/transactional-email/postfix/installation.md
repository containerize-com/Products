---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

#### **Install Postfix on Ubuntu**

Postfix is included in Ubuntu’s default repositories, so installation is incredibly simple.

To begin, update your local `apt` package cache and then install the software. We will be passing in the `DEBIAN_PRIORITY=low` environmental variable into our installation command in order to answer some additional prompts:

 ```
sudo apt-get update
sudo DEBIAN_PRIORITY=low apt-get install postfix
```

Use the following information to fill in your prompts correctly for your environment:

- General type of mail configuration?: For this, we will choose Internet Site since this matches our infrastructure needs.
- System mail name: This is the base domain used to construct a valid email address when only the account portion of the address is given. For instance, the hostname of our server is `mail.example.com`, but we probably want to set the system mail name to `example.com` so that given the username `user1`, Postfix will use the address `<span id="cloak939888f102c844e786c95e32ef264a8c">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloak939888f102c844e786c95e32ef264a8c').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addy939888f102c844e786c95e32ef264a8c='&#117;s&#101;r1'+'&#64;';addy939888f102c844e786c95e32ef264a8c=addy939888f102c844e786c95e32ef264a8c+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';var addy_text939888f102c844e786c95e32ef264a8c='&#117;s&#101;r1'+'&#64;'+'&#101;x&#97;mpl&#101;'+'&#46;'+'c&#111;m';document.getElementById('cloak939888f102c844e786c95e32ef264a8c').innerHTML+='<a '+path+'\''+prefix+':'+addy939888f102c844e786c95e32ef264a8c+'\'>'+addy_text939888f102c844e786c95e32ef264a8c+'<\/a>';</script>`.
- Root and postmaster mail recipient: This is the Linux account that will be forwarded mail addressed to `root@` and `postmaster@`. Use your primary account for this. In our case, sammy.
- Other destinations to accept mail for: This defines the mail destinations that this Postfix instance will accept. If you need to add any other domains that this server will be responsible for receiving, add those here, otherwise, the default should work fine.
- Force synchronous updates on mail queue?: Since you are likely using a journaled filesystem, accept No here.
- Local networks: This is a list of the networks that your mail server is configured to relay messages for. The default should work for most scenarios. If you choose to modify it, make sure to be very restrictive in regards to the network range.
- Mailbox size limit: This can be used to limit the size of messages. Setting it to “0” disables any size restriction.
- Local address extension character: This is the character that can be used to separate the regular portion of the address from an extension (used to create dynamic aliases).
- Internet protocols to use: Choose whether to restrict the IP version that Postfix supports. We’ll pick “all” for our purposes.
 
To be explicit, these are the settings we’ll use for this guide:

- General type of mail configuration?: Internet Site
- System mail name: example.com (not mail.example.com)
- Root and postmaster mail recipient: sammy
- Other destinations to accept mail for: $myhostname, example.com, mail.example.com, localhost.example.com, localhost
- Force synchronous updates on mail queue?: No
- Local networks: 127.0.0.0/8 \[::ffff:127.0.0.0\]/104 \[::1\]/128
- Mailbox size limit: 0
- Local address extension character: +
- Internet protocols to use: all
 
If you need to ever return to re-adjust these settings, you can do so by typing:

 ```
$  sudo dpkg-reconfigure postfix
```

The prompts will be pre-populated with your previous responses.

When you are finished, we can now do a bit more configuration to set up our system how we’d like it.
