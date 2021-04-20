---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once pre-requisites are in place, open the command line and run and check dependencies are satisfied and various paths correctly set to find different libraries and include files.

Now, build `Makefile`:

 ```
<pre class="wp-block-preformatted">```
qmake PREFIX=/usr/local/<br></br>
```
```

Compile `shotcut`:

 ```
make -j8 <br></br>
```

Then, run the following command:

 ```
make install
```

Finally, run `shotcut` from a build folder without installing you can make a symbolic link to the `qml` folder. It depends on where you build folder is, but assuming it is a sibling of the source tree folder:

 ```
cd build<br data-rich-text-line-break="true"></br>mkdir -p share/shotcut<br data-rich-text-line-break="true"></br>cd share/shotcut<br data-rich-text-line-break="true"></br>ln -s ../../../shotcut/src/qml
``````

```

####  

#### **Explore**

You may find the following links relevant:

- **[ Top 5 Open Source Video Editor Software For Video Marketing](https://blog.containerize.com/2021/01/08/top-5-open-source-video-editor-software-for-video-marketing/)**
- **[ A Beginners Guide To Start Video Editing With Free OpenShot](https://blog.containerize.com/2020/12/30/a-beginners-guide-to-start-video-editing-with-free-openshot/)**
- **[ How Video Editing Software Improves Business Video Marketing](https://blog.containerize.com/2020/12/18/how-video-editing-software-improves-business-video-marketing/)**
 