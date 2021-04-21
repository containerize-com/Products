---
title: Installation Guide
onpagelink: installation
weight: 3

---

#### **Installation Instructions**

Once all the prerequisites are installed, extract the Boost into a folder, note the location, and run the following command to ensure that your `BOOST_ROOT` environment points to the directory created by the Boost installation:

 ```
<pre class="wp-block-preformatted">```
cd /LOCATION/OF/YOUR/BOOST/DIRECTORY<br data-rich-text-line-break="true"></br>./bootstrap.sh<br data-rich-text-line-break="true"></br>./b2 cxxflags="-std=c++14"
```
```

Then, edit below code with your Boost directory location and run to add Boost environment variable to your `.bash_profile` file so it's automatically set when you log in.

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="ace783fa-9354-4d21-9dff-cc089ca68cdc" data-title="Preformatted" data-type="core/preformatted" id="block-ace783fa-9354-4d21-9dff-cc089ca68cdc" spellcheck="false" tabindex="0">```
echo "export BOOST_ROOT=/Users/my_user/boost_1_71_0" >> ~/.bash_profile
```
```

If you updated your `.bash_profile` file in the previous step, be sure to source it in a new Terminal window. For example:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable is-hovered wp-block" contenteditable="true" data-block="50962945-5ea3-4393-aa62-1a08a091a010" data-title="Preformatted" data-type="core/preformatted" id="block-50962945-5ea3-4393-aa62-1a08a091a010" tabindex="0">```
source .bash_profile
```
```

After that, run the following command to clone the app

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
git clone <span id="cloakc45530cf67b31ec2907713bebc03f608">This email address is being protected from spambots. You need JavaScript enabled to view it.</span><script type="text/javascript">document.getElementById('cloakc45530cf67b31ec2907713bebc03f608').innerHTML='';var prefix='&#109;a'+'i&#108;'+'&#116;o';var path='hr'+'ef'+'=';var addyc45530cf67b31ec2907713bebc03f608='g&#105;t'+'&#64;';addyc45530cf67b31ec2907713bebc03f608=addyc45530cf67b31ec2907713bebc03f608+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';var addy_textc45530cf67b31ec2907713bebc03f608='g&#105;t'+'&#64;'+'g&#105;th&#117;b'+'&#46;'+'c&#111;m';document.getElementById('cloakc45530cf67b31ec2907713bebc03f608').innerHTML+='<a '+path+'\''+prefix+':'+addyc45530cf67b31ec2907713bebc03f608+'\'>'+addy_textc45530cf67b31ec2907713bebc03f608+'<\/a>';</script>:ripple/rippled.git
```
```

For the latest stable release, use the `master` branch.

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
cd rippled<br data-rich-text-line-break="true"></br>git checkout master
```
```

Now, in the root directory, run the following commands:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
mkdir my_build<br data-rich-text-line-break="true"></br>cd my_build
```
```

Now, generate the build by running the following comands:

 ```
cmake -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Debug ..
```

Then, run the build using CMake. This could take about 10 minutes

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
cmake --build . -- -j 4 
```
```

 `rippled` requires the `rippled.cfg` config file to run. You can find an example config file, `rippled-example.cfg` in `rippled/cfg`. Make a copy and save it as `rippled.cfg` in a location that enables you to run `rippled` as a non-root user. Access the `rippled` directory and run:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">mkdir -p $HOME/.config/ripple<br data-rich-text-line-break="true"></br>```
cp cfg/rippled-example.cfg $HOME/.config/ripple/rippled.cfg
```
```

Edit `rippled.cfg` to set necessary file paths. The user you plan to run `rippled` as must have write permissions to all of the paths you specify here.

Set the `[node_db]`, `[database_path]` and \[debug\_logfile\]

`Rippled` requires the `validators.txt` file to run. You can find an example validators file, `validators-example.txt`, in `rippled/cfg/`. Make a copy and save it as `validators.txt` in the same folder as your `rippled.cfg` file. Access the `rippled` directory and run:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
cp cfg/validators-example.txt $HOME/.config/ripple/validators.txt
```
```

Finally, access your build directory and start the rippled with the following command:

 ```
<pre class="wp-block-preformatted block-editor-block-list__block wp-block is-selected rich-text block-editor-rich-text__editable wp-block" contenteditable="true" data-block="dc6954d0-8331-4d63-8139-ed9408a894fb" data-title="Preformatted" data-type="core/preformatted" id="block-dc6954d0-8331-4d63-8139-ed9408a894fb" spellcheck="false" tabindex="0">```
 ./rippled 
```
```

####  

#### **Explore**

You may find the following links relevant:

- **[ A Beginners Guide To Setup Ethereum Node On Localhost](https://blog.containerize.com/2020/12/23/a-beginners-guide-to-setup-ethereum-node-on-localhost/)**
- **[ Top 5 Open Source Blockchain Platforms In 2020](https://blog.containerize.com/2020/12/11/top-5-open-source-blockchain-platforms-in-2020/)**
- **[ A Basic Guide on How To Create Ethereum Smart Contract](https://blog.containerize.com/2020/12/01/a-basic-guide-on-how-to-create-ethereum-smart-contract/)**
- **[How Blockchain Technology Can Upgrade Your Business Strategy](https://blog.containerize.com/2020/11/27/how-blockchain-technology-can-upgrade-your-business-strategy/)**
 