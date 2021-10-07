---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

The best way to get started locally with Botkit is by installing our command line tool, and using it to create a new Botkit project. This will install and configure a starter kit for you!

 ```
npm install -g yo generator-botkit
yo botkit
```

#### Start from Scratch

You can also add Botkit into an existing Node application.

First, add it to your project:

 ```
npm install --save botkit
```

Then, add Botkit to your application code:

 ```
let { Botkit } = require('botkit');

const controller = new Botkit(MY_CONFIGURATION);

controller.hears('hello','direct_message', function(bot, message) {
    bot.reply(message,'Hello yourself!');
});
```
