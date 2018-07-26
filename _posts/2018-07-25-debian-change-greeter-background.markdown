---
layout: post
title:  "Debian Change Greeter Background"
date:   2018-07-25 19:11:00 -0500
categories: linux debian
---
To change the greeter cd to `/etc/lightdm` and open `lightdm-gtk-greeter.conf` in a text editor.

Uncomment the stub just below `[greeter]` labeled `background=` and append the path and file name to the desired image. For example, something like this: `background=/home/<user>/Pictures/Wallpapers/image-name.png`. Reboot the system.
