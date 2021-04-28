---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once all the pre-requisites are installed, use the following commands to clone the source code:

 ```
<pre class="wp-block-preformatted">```
git clone https://github.com/OpenShot/libopenshot-audio.git<br data-rich-text-line-break="true"></br>git clone https://github.com/OpenShot/libopenshot.git<br data-rich-text-line-break="true"></br>git clone https://github.com/OpenShot/openshot-qt.git<br></br>
```
```

In order to actually compile or run OpenShot, we need to install some dependencies on your system

 ```
sudo add-apt-repository ppa:openshot.developers/libopenshot-daily<br data-rich-text-line-break="true"></br>sudo apt-get update<br></br>sudo apt-get install openshot-qt \<br data-rich-text-line-break="true"></br>cmake \ libx11-dev \ libasound2-dev \ libavcodec-dev \ libavdevice-dev \ libavfilter-dev \<br data-rich-text-line-break="true"></br>libavformat-dev \ libavresample-dev \ libavutil-dev \ libfdk-aac-dev \ libfreetype6-dev \<br data-rich-text-line-break="true"></br>libjsoncpp-dev \ libmagick++-dev \ libopenshot-audio-dev \ libswscale-dev \ libunittest++-dev \<br data-rich-text-line-break="true"></br>libxcursor-dev \ libxinerama-dev \ libxrandr-dev \ libzmq3-dev \ pkg-config \ python3-dev \<br data-rich-text-line-break="true"></br>qtbase5-dev \ qtmultimedia5-dev \ swig
```

At this point, you should have all 3 OpenShot components source code cloned into local folders. Now, run the following commands to build and install libopenshot-audio:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="50962945-5ea3-4393-aa62-1a08a091a010" data-title="Preformatted" data-type="core/preformatted" id="block-50962945-5ea3-4393-aa62-1a08a091a010" tabindex="0">```
cd libopenshot-audio<br data-rich-text-line-break="true"></br>mkdir build<br data-rich-text-line-break="true"></br>cd build<br data-rich-text-line-break="true"></br>cmake ../<br data-rich-text-line-break="true"></br>make install
```
```

<span style="font-size: 12.16px;">Now, we are switching to the libopenshot-audio/build folder, and running `cmake ../` on the parent folder. However, this folder finds dependencies and creates all the needed Makefiles used to compile this library. Then `make install` uses those Makefiles to compile, and install this library. Therefore, this should result in files being installed to your **/usr/local/** folder.</span>

Then, run the following commands to build and install libopenshot:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
cd libopenshot<br data-rich-text-line-break="true"></br>mkdir build<br data-rich-text-line-break="true"></br>cd build<br data-rich-text-line-break="true"></br>cmake ../<br data-rich-text-line-break="true"></br>make install<br data-rich-text-line-break="true"></br>sudo ldconfig
```
```

Now, we are switching to the libopenshot/build folder, and running `cmake ../` on the parent folder. However, this folder finds dependencies and creates all the needed Makefiles used to compile this library. Then `make install` uses those Makefiles to compile, and install this library. After that, this should result in files being installed to your **/usr/local/** folder and in your Python site-packages folder. However, the ldconfig command updates the system's library cache.

To launch openshot-qt from the source code, use the following commands:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
cd openshot-qt<br data-rich-text-line-break="true"></br>python3 src/launch.py
```
```

Finally, this will launch the OpenShot user interfac.

#### **Explore**

You may find the following links relevant:

- **[ Top 5 Open Source Video Editor Software For Video Marketing](https://blog.containerize.com/2021/01/08/top-5-open-source-video-editor-software-for-video-marketing/)**
- **[ A Beginners Guide To Start Video Editing With Free OpenShot](https://blog.containerize.com/2020/12/30/a-beginners-guide-to-start-video-editing-with-free-openshot/)**
- **[ How Video Editing Software Improves Business Video Marketing](https://blog.containerize.com/2020/12/18/how-video-editing-software-improves-business-video-marketing/)**
 