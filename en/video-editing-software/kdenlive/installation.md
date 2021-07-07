---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

For Ubuntu, run the following commands to pull all the dependencies:

    sudo apt install libkf5archive-dev libkf5bookmarks-dev libkf5coreaddons-dev libkf5config-dev \
    libkf5configwidgets-dev libkf5dbusaddons-dev libkf5kio-dev libkf5widgetsaddons-dev \
    libkf5notifyconfig-dev libkf5newstuff-dev libkf5xmlgui-dev libkf5declarative-dev \
    libkf5notifications-dev libkf5guiaddons-dev libkf5textwidgets-dev libkf5purpose-dev \
    libkf5iconthemes-dev kdoctools-dev libkf5crash-dev libkf5filemetadata-dev  kio \
    kinit qtdeclarative5-dev libqt5svg5-dev qml-module-qtquick-controls \
    qtmultimedia5-dev qtquickcontrols2-5-dev breeze-icon-theme

    sudo apt install libmlt++-dev libmlt-dev melt frei0r-plugins ffmpeg

    sudo apt install ruby subversion gnupg2 gettext 

Now, run the following command to clone the source code of the Kdenlive:

    git clone https://invent.kde.org/multimedia/kdenlive

Then , checkout to the master branch:

    cd kdenlive
    git checkout master

After that, create a directory for the build inside the kdenlive directory:

    mkdir build
    cd build

Moreover, It is easier to install Kdenlive in /usr to avoid problems with plugins and libraries:

    cmake .. -DKDE_INSTALL_USE_QT_SYS_PATHS=ON -DCMAKE_INSTALL_PREFIX=/usr -DRELEASE_BUILD=OFF

Run the following command to fetch the translations of the application :

    make fetch-translations

Above command will create a po sub-directory in your build directory. After that, run the following commands to create symbolic link to this po subdirectory :

    cd ..
    ln -s build/po/ po
    cd build/

In the last, install and build by running the following commands:

    make -j5
    sudo make install

Finally, start your compiled version:

    kdenlive

