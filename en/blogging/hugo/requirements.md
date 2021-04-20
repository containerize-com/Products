---
title: Requirements
onpagelink: requirements
weight: 1

---

Requirements
------------

1. Hugo runs on a standard version of all major desktop operating systems - Windows, MacOS and the various flavors of Unix.
2. You need to have Go installed to use Hugo modules. If you plan to not use Hugo modules and manually place the theme in the themes folder of the website, then Go installation is not required. If Hugo isd installed via the package manager, the package manager takes care of installing the Go Language. The installation instruction for Go are present at golang.org/doc/install. You do not need to learn Go or use it directly within Hugo.
3. While git is not required to use Hugo, if git is used as a version control system, Hugo provides access to the metadata in the templates. Git is available in all package managers as git. You can also get git from git-scm.com/. You can learn more about git from Git in Practice and Learn Git in a Month of Lunches.
 
Features
--------

<div class="col-lg-12">Hugo boasts blistering speed, robust content management, and a powerful templating language making it a great fit for all kinds of static websites.

### General

- Extremely fast build times (&lt; 1 ms per page)
- Completely cross platform, with easy installation on macOS, Linux, Windows, and more
- Renders changes on the fly with LiveReload as you develop
- Powerful theming
- Host your site anywhere
 
### Organization

- Straightforward organization for your projects, including website sections
- Customizable URLs
- Support for configurable taxonomies, including categories and tags
- Sort content as you desire through powerful template functions
- Automatic table of contents generation
- Dynamic menu creation
- Pretty URLs support
- Permalink pattern support
- Redirects via aliases
 
### Content

- Native Markdown and Emacs Org-Mode support, as well as other languages via external helpers (see supported formats)
- TOML, YAML, and JSON metadata support in front matter
- Customizable homepage
- Multiple content types
- Automatic and user defined content summaries
- Shortcodes to enable rich content inside of Markdown
- “Minutes to Read” functionality
- “WordCount” functionality
 
### Additional Features

- Integrated Disqus comment support
- Integrated Google Analytics support
- Automatic RSS creation
- Support for Go HTML templates
- Syntax highlighting powered by Chroma
 
 </div><div class="col-lg-12">Installation Guide
------------------

Install Hugo on macOS, Windows, Linux, OpenBSD, FreeBSD, and on any machine where the Go compiler tool chain can run.

Hugo is written in Go with support for multiple platforms. The latest release can be found at Hugo Releases.

Hugo currently provides pre-built binaries for the following:

- macOS (Darwin) for x64, i386, and ARM architectures
- Windows
- Linux
- OpenBSD
- FreeBSD
 
Hugo may also be compiled from source wherever the Go toolchain can run; e.g., on other operating systems such as DragonFly BSD, OpenBSD, Plan 9, Solaris, and others. See https://golang.org/doc/install/source for the full set of supported combinations of target operating systems and compilation architectures.

### Quick Install

#### Binary (Cross-platform)

Download the appropriate version for your platform from Hugo Releases. Once downloaded, the binary can be run from anywhere. You don’t need to install it into a global location. This works well for shared hosts and other systems where you don’t have a privileged account.   
 Ideally, you should install it somewhere in your `PATH` for easy use. `/usr/local/bin` is the most probable location.

#### Docker

We currently do not offer official Hugo images for Docker, but we do recommend these up to date distributions:  
 https://hub.docker.com/r/klakegg/hugo/

#### Homebrew (macOS)

If you are on macOS and using Homebrew, you can install Hugo with the following one-liner:

 `install-with-homebrew.sh` ```
brew install hugo
```

 ```
For more detailed explanations, read the installation guides that follow for installing on macOS and Windows.
```

#### MacPorts (macOS)

If you are on macOS and using MacPorts, you can install Hugo with the following one-liner:

 `install-with-macports.sh` ```
port install hugo
```

#### Homebrew (Linux)

If you are using Homebrew on Linux, you can install Hugo with the following one-liner:

 `install-with-linuxbrew.sh` ```
brew install hugo
```

 ```
Installation guides for Homebrew on Linux are available on their website.
```

#### Chocolatey (Windows)

If you are on a Windows machine and use Chocolatey for package management, you can install Hugo with the following one-liner:

 `install-with-chocolatey.ps1` ```
choco install hugo -confirm
```

Or if you need the “extended” Sass/SCSS version:

 `install-extended-with-chocolatey.ps1` ```
choco install hugo-extended -confirm
```

#### Scoop (Windows)

If you are on a Windows machine and use Scoop for package management, you can install Hugo with the following one-liner:

 ```
scoop install hugo
```

Or install the extended version with:

 ```
scoop install hugo-extended
```

 </div>