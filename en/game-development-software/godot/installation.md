---
title: Installation Guide
onpagelink: installation
weight: 3

---


### **Installation Instructions**

Once all the pre-requisites are installed, run the following command in the terminal to clone the source code:

    git clone https://github.com/godotengine/godot.git

After that, go to the root directory of the engine source code and run the following command to compile for Intel (x86-64) powered Macs:

    scons platform=osx arch=x86_64 --jobs=$(sysctl -n hw.logicalcpu)

Run the following command to compile for Apple Silicon (ARM64) powered Macs:

    scons platform=osx arch=arm64 --jobs=$(sysctl -n hw.logicalcpu)

Then, run the following command:

    lipo -create bin/godot.osx.tools.x86_64 bin/godot.osx.tools.arm64 -output bin/godot.osx.tools.universal

Finally, find the executable binary in to the bin/ subdirectory.


