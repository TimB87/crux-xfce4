

INSTRUCTIONS INSTALLING CRUX-XFCE4 REPO
=====
1. First download the necessary files:

   ```bash
   wget --no-ch https://raw.githubusercontent.com/mac-a-r0ni/crux-xfce4/master/crux-xfce4.httpup
   ```

2. Move the downloaded file to the proper folder:

   ```bash
   sudo mv crux-xfce4.httpup /etc/ports/
   ```

 4. Create the dir where the ports are contained:
    ```bash
    sudo mkdir /usr/ports/crux-xfce4
    ```

4. Add the ports line in yours */etc/prt-get.conf* to fetch the repo:

   prtdir /usr/ports/crux-xfce4

5. Update the repo into your computer:

   ```bash
   sudo ports -u crux-xfce4
   ```

NOTES
=====
1. Enable the contrib repo because some dependencies reside there.
2. The XFCE 4.18 Desktop has been tested on CRUX/CRUX-ARM 3.7. You may need to ignore footprints if youve installed certain software from the official repos. 

CONTACT
=====
If you have any questions, doubts or problems regarding the ports, please feel free to contact me at j at lngn dot net or just open a [issue](https://github.com/mac-a-r0ni/crux-xfce4/issues).

XFCE INSTALLATION
=====
1. To ensure you have a sane Xorg installation I decided to put all the Xorg dependencies with the first package you install from XFCE on **libxfce4util**
2. Install the packages in this **exact order**:

   ```bash
   sudo prt-get depinst libxfce4util xfconf libxfce4ui udisks2 gvfs garcon exo xfce4-panel thunar thunar-volman xfce4-settings xfce4-session xfwm4 xfdesktop xfce4-appfinder tumbler xfce4-terminal xfce4-power-manager xfce4-notifyd xfce4-screenshooter mousepad xdg-user-dirs
   ```

3. Get a big cup of coffee and just relax...

4. To launch Xfce create a *.xinitrc* file in your *home* directory with the following content:
   ```bash
   #!/bin/sh
   exec ck-launch-session startxfce4
   ```
   
5. If you have any problem launching XFCE and you have a an Intel graphic card, install **xorg-xf86-video-intel** and the **mesa** ports from the xorg repo.

6. Enjoy this beautiful Desktop Environment!
