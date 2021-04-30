---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once all the pre-requisites are installed, use the following commands to clone the source code:

    git clone https://github.com/OpenShot/libopenshot-audio.gitgit clone https://github.com/OpenShot/libopenshot.gitgit clone https://github.com/OpenShot/openshot-qt.git

In order to actually compile or run OpenShot, we need to install some dependencies on your system

    sudo add-apt-repository ppa:openshot.developers/libopenshot-dailysudo apt-get updatesudo apt-get install openshot-qt \cmake \ libx11-dev \ libasound2-dev \ libavcodec-dev \ libavdevice-dev \ libavfilter-dev \libavformat-dev \ libavresample-dev \ libavutil-dev \ libfdk-aac-dev \ libfreetype6-dev \libjsoncpp-dev \ libmagick++-dev \ libopenshot-audio-dev \ libswscale-dev \ libunittest++-dev \libxcursor-dev \ libxinerama-dev \ libxrandr-dev \ libzmq3-dev \ pkg-config \ python3-dev \qtbase5-dev \ qtmultimedia5-dev \ swig

At this point, you should have all 3 OpenShot components source code cloned into local folders. Now, run the following commands to build and install libopenshot-audio:

    cd libopenshot-audiomkdir buildcd buildcmake ../make install

Now, we are switching to the libopenshot-audio/build folder, and running `cmake ../` on the parent folder. However, this folder finds dependencies and creates all the needed Makefiles used to compile this library. Then `make install` uses those Makefiles to compile, and install this library. Therefore, this should result in files being installed to your **/usr/local/** folder.

Then, run the following commands to build and install libopenshot:

    cd libopenshotmkdir buildcd buildcmake ../make installsudo ldconfig

Now, we are switching to the libopenshot/build folder, and running `cmake ../` on the parent folder. However, this folder finds dependencies and creates all the needed Makefiles used to compile this library. Then `make install` uses those Makefiles to compile, and install this library. After that, this should result in files being installed to your **/usr/local/** folder and in your Python site-packages folder. However, the ldconfig command updates the system's library cache.

To launch openshot-qt from the source code, use the following commands:

    cd openshot-qtpython3 src/launch.py

Finally, this will launch the OpenShot user interfac.

