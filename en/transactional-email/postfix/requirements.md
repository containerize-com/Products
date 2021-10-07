---
title: System Requirements
onpagelink: requirements
weight: 1

---

### **System Requirements**

The Postfix mail queue requires that:

- Renaming a file to a near-by directory does not change the file's inode number.
- A file is not lost after fsync() of that file (not its parent directory) returns successfully, and then the system crashes. This must be true even when that file is later renamed to a near-by directory.
- When Postfix in a virtual guest machine flushes a file with fsync(), the file information must not be cached in volatile host memory. Instead the information must immediately be written to disk (or to persistent cache) before fsync() returns in the virtual guest machine.
- Postfix can set the execute bit on a queue file. If this does not work, then no mail will ever be delivered.
 
In addition to the above, Postfix maildir delivery requires that:

- A file can be hard linked between different near-by directories.
- A file is not lost when it is hard-linked to a near-by directory, unlinked from the old directory, and then the system crashes.
 
Postfix mailbox delivery introduces no additional requirements.

Files in the Postfix command\_directory require that:

- The setgid bit works. This is required to access the mail queue with the postdrop command, and to access protected UNIX-domain sockets with the postdrop and postqueue commands.
 
