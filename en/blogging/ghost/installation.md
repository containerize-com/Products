---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Guide
------------------

### Install Node.js

Ghost Blog is powered by Node.js. Hence, we have to download and install Node.js LTS version from the official website.

### Install Ghost command line tool

Open the terminal and execute the following commands. It will install ghost command line tool using npm package manager.

 ```
 $ sudo npm install -g ghost-cli 
```

### Install Ghost command line tool

Navigate to `~/Documents` directory and create an empty folder ghost to install Ghost.

 ```

$ cd ~/Documents
$ mkdir ghost
```

Then, navigate into the ghost folder and print current working directory to make sure you are at `/Users/[username]/Documents/ghost`.

 ```

$ cd ghost 
$ pwd
/Users/[username]/Documents/ghost

```

Next, install local version of ghost.

 ```

$ ghost install local

```

### Setup an admin account

Now copy paste the 2nd URL in the terminal into your browser to setup the admin account for Ghost. In my case, the URL is

 ```

http://localhost:2368/ghost/

```

You will see the welcome page to setup the Ghost admin account.

After going through the setup process of admin account, you will be able to see the admin dashboard.

### Try it out!

Congratulations, now you have successfully setup the ghost blog locally! Feel free to experiment it out as you like. Try publishing some dummy blog post   
  
 And proceed to `http://localhost:2368/` to view your blog posts. In case you haven’t notice, it is the same URL as admin page without the `/ghost/`.   
  
 Boom! The test blog post has been successfully added.

### Start/Stop the ghost blog

To stop the Ghost blog server, simply head back to the terminal and execute

 ```
 $ ghost stop 
```

Make sure you are at `~/Documents/ghost/` directory when executing the command above.  
  
 Now the Ghost Blog is not available at the URL anymore. To start Ghost again next time, simply go to `~/Documents/ghost/` directory to start the local server.

 ```

$ cd ~/Documents/ghost/
$ ghost start 
```

**That's it! Congrats Ghost is install now**