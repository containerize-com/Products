---
title: Installation Guide
onpagelink: installation
weight: 3

---

### **Installation Instructions**

Once all the prerequisites are installed, extract the Boost into a folder, note the location, and run the following command to ensure that your `BOOST_ROOT` environment points to the directory created by the Boost installation:

    cd /LOCATION/OF/YOUR/BOOST/DIRECTORY./bootstrap.sh./b2 cxxflags="-std=c++14"

Then, edit below code with your Boost directory location and run to add Boost environment variable to your `.bash_profile` file so it's automatically set when you log in.

    echo "export BOOST_ROOT=/Users/my_user/boost_1_71_0" >> ~/.bash_profile

If you updated your `.bash_profile` file in the previous step, be sure to source it in a new Terminal window. For example:

    source .bash_profile

After that, run the following command to clone the app

        git clone git@github.com:ripple/rippled.git

For the latest stable release, use the `master` branch.

    cd rippledgit checkout master

Now, in the root directory, run the following commands:

    mkdir my_buildcd my_build

Now, generate the build by running the following comands:

    cmake -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Debug ..

Then, run the build using CMake. This could take about 10 minutes

    cmake --build . -- -j 4 

 `rippled` requires the `rippled.cfg` config file to run. You can find an example config file, `rippled-example.cfg` in `rippled/cfg`. Make a copy and save it as `rippled.cfg` in a location that enables you to run `rippled` as a non-root user. Access the `rippled` directory and run:

mkdir -p $HOME/.config/ripple  
`cp cfg/rippled-example.cfg $HOME/.config/ripple/rippled.cfg`

Edit `rippled.cfg` to set necessary file paths. The user you plan to run `rippled` as must have write permissions to all of the paths you specify here.

Set the `[node_db]`, `[database_path]` and \[debug\_logfile\]

`Rippled` requires the `validators.txt` file to run. You can find an example validators file, `validators-example.txt`, in `rippled/cfg/`. Make a copy and save it as `validators.txt` in the same folder as your `rippled.cfg` file. Access the `rippled` directory and run:

    cp cfg/validators-example.txt $HOME/.config/ripple/validators.txt

Finally, access your build directory and start this distributed infrastructure rippled with the following command:

     ./rippled 

