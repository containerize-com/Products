---
title: Installation
onpagelink: installation
weight: 3

---

### Installation

- Use following command to download wine from the Ubuntu repository:
 
 ```
sudo apt-get install wine
```

- Then download HeidiSQL installer from http://www.heidisql.com/download.php
- After that open the installer for HeidiSQL with Wine.
- Then find out where Wine is storing the HeidiSQL icon. In my instance, it was in /home/nic/.local/share/icons/hicolor/48x48/apps.
- Also find the location of the HeidiSQL executable. In my instance, it’s in /home/nic/.wine/drive\_c/Program Files/HeidiSQL.
- Create a new file in ~/.local/share/applications, called heidisql.desktop using following command:
 
 ```
sudo gedit ~/.local/share/applications/heidisql.desktop
```

- Add following code in this file:
 
 ```
[Desktop Entry]
Name=HeidiSQL
Comment=HeidiSQL on Ubuntu
Exec=env WINEDEBUG=-all WINEPREFIX=/home/USER/.wine wine heidisql.exe
Icon=/home/USER/.local/share/icons/hicolor/48x48/apps/9103_heidisql.0.png
Path=/home/USER/.wine/drive_c/Program Files/HeidiSQL
Terminal=false
Type=Application
Categories=Wine;
StartupNotify=true
StartupWMClass=heidisql.exe
```

- Change the paths after Exec=, Icon= and Path= accordingly.
- Search for HeidiSQL in Dash and drag the icon from there.
- Finally open HeidiSQL dashboard using the icon and connect to your databases.
 