---
title: Installation Guide
onpagelink: installation
weight: 3

---

### Installation Instructions

#### Installing Exim binaries and scripts

The command make install runs the exim\_install script with no arguments. The script copies binaries and utility scripts into the directory whose name is specified by the BIN\_DIRECTORY setting in Local/Makefile. The install script copies files only if they are newer than the files they are going to replace. The Exim binary is required to be owned by root and have the setuid bit set, for normal configurations. Therefore, you must run make install as root so that it can set up the Exim binary in this way. However, in some special situations (for example, if a host is doing no local deliveries) it may be possible to run Exim without making the binary setuid root (see chapter 56 for details).

Exim’s runtime configuration file is named by the CONFIGURE\_FILE setting in Local/Makefile. If this names a single file, and the file does not exist, the default configuration file src/configure.default is copied there by the installation script. If a runtime configuration file already exists, it is left alone. If CONFIGURE\_FILE is a colon-separated list, naming several alternative files, no default is installed.

One change is made to the default configuration file when it is installed: the default configuration contains a router that references a system aliases file. The path to this file is set to the value specified by SYSTEM\_ALIASES\_FILE in Local/Makefile (/etc/aliases by default). If the system aliases file does not exist, the installation script creates it, and outputs a comment to the user.

The created file contains no aliases, but it does contain comments about the aliases a site should normally have. Mail aliases have traditionally been kept in /etc/aliases. However, some operating systems are now using /etc/mail/aliases. You should check if yours is one of these, and change Exim’s configuration if necessary.

The default configuration uses the local host’s name as the only local domain, and is set up to do local deliveries into the shared directory /var/mail, running as the local user. System aliases and .forward files in users’ home directories are supported, but no NIS or NIS+ support is configured. Domains other than the name of the local host are routed using the DNS, with delivery over SMTP.

It is possible to install Exim for special purposes (such as building a binary distribution) in a private part of the file system. You can do this by a command such as

 ```
make DESTDIR=/some/directory/ install
```

This has the effect of pre-pending the specified directory to all the file paths, except the name of the system aliases file that appears in the default configuration. (If a default alias file is created, its name is modified.) For backwards compatibility, ROOT is used if DESTDIR is not set, but this usage is deprecated.

Running make install does not copy the Exim 4 conversion script convert4r4. You will probably run this only once if you are upgrading from Exim 3. None of the documentation files in the doc directory are copied, except for the info files when you have set INFO\_DIRECTORY, as described in section 4.17 below.

For the utility programs, old versions are renamed by adding the suffix .O to their names. The Exim binary itself, however, is handled differently. It is installed under a name that includes the version number and the compile number, for example, exim-4.94-1. The script then arranges for a symbolic link called exim to point to the binary. If you are updating a previous version of Exim, the script takes care to ensure that the name exim is never absent from the directory (as seen by other processes).

If you want to see what the make install will do before running it for real, you can pass the -n option to the installation script by this command:

 ```
make INSTALL_ARG=-n install
```

The contents of the variable INSTALL\_ARG are passed to the installation script. You do not need to be root to run this test. Alternatively, you can run the installation script directly, but this must be from within the build directory. For example, from the top-level Exim directory you could use this command:

 ```
(cd build-SunOS5-5.5.1-sparc; ../scripts/exim_install -n)
```

There are two other options that can be supplied to the installation script.

- -no\_chown bypasses the call to change the owner of the installed binary to root, and the call to make it a setuid binary.
- -no\_symlink bypasses the setting up of the symbolic link exim to the installed binary.
 
INSTALL\_ARG can be used to pass these options to the script. For example:

 ```
make INSTALL_ARG=-no_symlink install
```

The installation script can also be given arguments specifying which files are to be copied. For example, to install just the Exim binary, and nothing else, without creating the symbolic link, you could use:

 ```
make INSTALL_ARG='-no_symlink exim' install
```

#### Installing info documentation

Not all systems use the GNU info system for documentation, and for this reason, the Texinfo source of Exim’s documentation is not included in the main distribution. Instead it is available separately from the FTP site (see section 1.5).

If you have defined INFO\_DIRECTORY in Local/Makefile and the Texinfo source of the documentation is found in the source tree, running make install automatically builds the info files and installs them.