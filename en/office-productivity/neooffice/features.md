---
title: Features
onpagelink: features
weight: 1

---

Features
--------

### Native Dark Mode

In macOS Mojave, Apple added native Dark Mode. The NeoOffice engineers have implemented this Mac feature and NeoOffice will automatically use the macOS Dark Mode colors when you enable macOS Dark Mode.

### Open at Launch menu to open Calc or Impress instead of Writer at launch

The NeoOffice &gt; Open at Launch menu allows you to choose which type of document to open when NeoOffice is launched. By default, NeoOffice opens a Writer document when launched. However, many of our users have requested that we provide an easy way to make a different document type such as Calc or Impress open when NeoOffice is launched so we have added the NeoOffice &gt; Open at Launch menu.

When a user selects one of the document types listed in this menu, NeoOffice will open the selected document type the next time that you launch it. Also, users can select the "- None -" menu item to only show the Mac menubar when NeoOffice is launched. The screen snapshot to the right shows the NeoOffice &gt; Open at Launch menu with Calc set as the document type to open at launch.

### File &gt; Browse All Versions menu to restore previous versions of your documents

In OS X Lion, Apple added a feature called Versions that allows applications to save and restore previous versions of your document. Using this feature, saving a document causes Mac to keep a copy of your document before any changes are saved so that you can restore any of the previous versions of your document.

The NeoOffice engineers have implemented this Mac feature and saving a file will automatically keep a copy of your document before any changes are saved. Also, by selecting NeoOffice's "Browse All Versions" menu, you will be able to restore any of the previous versions of your document in Apple's document version browser.

### Native Mac text highlighting

NeoOffice draws highlighted text the same as Apple's Safari and TextEdit applications. Recent versions of OpenOffice and LibreOffice attempt to emulate native Mac text highlighting by drawing a very light shade of the system highlight color on top of the highlighted text. However, many of our users have requested that we support full native Mac text highlighting behavior in NeoOffice so we have rewritten the text highlighting code in NeoOffice's underlying OpenOffice and LibreOffice code to draw highlighted text the same as Apple's various Mac applications. The following screen snapshots show how NeoOffice's text highlighting behavior compares to OpenOffice's behavior:

### Native file locking to safely edit files in iCloud Drive, Dropbox, or network drives

Because Microsoft Office and iCloud Drive use Mac native file locking, NeoOffice also uses Mac native file locking to prevent a collision when NeoOffice, Microsoft Office, or iCloud Drive users on different computers save the same file simultaneously.

### Support for Mac Services

In NeoOffice, many of the menus within the NeoOffice &gt; Services menu will be enabled whenever you highlight data in your document. When you select any of the submenus in the NeoOffice &gt; Services menu, the highlighted data will be sent to the Mac application that matches to the Services menu that you select. NeoOffice also supports Mac services that change the highlighted data in your document.

### Native floating tool windows

In OpenOffice and LibreOffice, many floating tool windows such as the Styles and Formatting and the Color windows look and behave like document windows. Also, other floating tool windows such as the Bullets and Numbering and the Table windows look and behave like Windows floating tool windows. But in NeoOffice, all floating tool windows in NeoOffice will be native floating tool windows. This means that they will look and behave like floating tool windows in most other Mac applications. They will have the small window titlebar, all of the floating tool windows will float above the document windows, and when NeoOffice is not the active application, all of the floating tool windows will automatically be hidden until NeoOffice becomes the active application again.