---
title: Requirements
onpagelink: requirements
weight: 1

---

Requirements
------------

Installing Hexo is quite easy and only requires the following beforehand:

1. Node.js (Should be at least Node.js 10.13, recommends 12.0 or higher)
2. Git
 
Features
--------

- Blazing Fast - Node.js brings you incredible generating speed. Hundreds of files take only seconds to build.
- Markdown Support - All features of GitHub Flavored Markdown are supported. You can even use most Octopress plugins in Hexo.
- One-Command Deployment - You only need one command to deploy your site to GitHub Pages, Heroku or other sites.
- Various Plugins - Hexo has a powerful plugin system. You can install more plugins for Jade, CoffeeScript plugins.
 
<div class="col-lg-12">
Installation Guide
------------------

Once all the requirements are installed, you can install Hexo with npm:

 ```
$ npm install -g hexo-cli
```

### Advanced installation and usage

Advanced users may prefer to install and use hexo package instead.

 ```
$ npm install hexo
```

Once installed, you can run Hexo in two ways:

1. `npx hexo <command></command>`
2. Linux users can set relative path of `node_modules/` folder:
 
 ```
echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
```

then run Hexo using `hexo <command></command>`

 </div>