---
title: Installation Guide
onpagelink: installation
weight: 3

---

Installation Guide
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