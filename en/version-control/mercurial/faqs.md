---
title: FAQs
onpagelink: faqs
weight: 4

---

### FAQs

### What is Mercurial?
Mercurial is a distributed version control system (DVCS). It is a cross-platform and written in Python. It allows source code management for projects of any size and type.
### What is tip in Mercurial?
The most recent changeset added to the repository is the tip. If you've recently made a commit, that will be the tip. If you've recently pulled something from another repository, the tip of that repository becomes the new tip. To see the repository's tip, type "hg tip".
### What is the difference between tip and head?
The tip is always a head. If a repository has many heads, only one of them is the tip. Changesets are numbered sequentially within a repository, with the tip having the greatest sequence number. 
### Is Mercurial open source?
Mercurial is a free and open source version control software like Git. You can download and install on your system. 
### How can you create a repository in Mercurial?
You can initialize the repository with init command like "hg init". It will create .hg directory inside respository.
