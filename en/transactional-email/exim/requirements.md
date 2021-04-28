---
title: System Requirements
onpagelink: requirements
weight: 1

---

### System Requirements

Before building Exim, a local configuration file that specifies options independent of any operating system has to be created with the name Local/Makefile. A template for this file is supplied as the file src/EDITME, and it contains full descriptions of all the option settings therein. These descriptions are therefore not repeated here. If you are building Exim for the first time, the simplest thing to do is to copy src/EDITME to Local/Makefile, then read it and edit it appropriately.

There are three settings that you must supply, because Exim will not build without them. They are the location of the runtime configuration file (CONFIGURE\_FILE), the directory in which Exim binaries will be installed (BIN\_DIRECTORY), and the identity of the Exim user (EXIM\_USER and maybe EXIM\_GROUP as well). The value of CONFIGURE\_FILE can in fact be a colon-separated list of filenames; Exim uses the first of them that exists.

There are a few other parameters that can be specified either at build time or at runtime, to enable the same binary to be used on a number of different machines. However, if the locations of Exim’s spool directory and log file directory (if not within the spool directory) are fixed, it is recommended that you specify them in Local/Makefile instead of at runtime, so that errors detected early in Exim’s execution (such as a malformed configuration file) can be logged.

Exim’s interfaces for calling virus and spam scanning software directly from access control lists are not compiled by default. If you want to include these facilities, you need to set

 ```
WITH_CONTENT_SCAN=yes
```

in your Local/Makefile. For details of the facilities themselves

If you are going to build the Exim monitor, a similar configuration process is required. The file exim\_monitor/EDITME must be edited appropriately for your installation and saved under the name Local/eximon.conf. If you are happy with the default settings described in exim\_monitor/EDITME, Local/eximon.conf can be empty, but it must exist.

This is all the configuration that is needed in straightforward cases for known operating systems. However, the building process is set up so that it is easy to override options that are set by default or by operating-system-specific configuration files, for example, to change the C compiler, which defaults to gcc.