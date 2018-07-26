---
layout: post
title:  "Debian Change Lock Screen Background"
date:   2018-07-25 20:02:00 -0500
categories: linux debian
---
I would call the following a hacky way of doing this but it works. Proceed with caution ;).

To change the lock screen background navigate to `/usr/share/desktop-base/active-theme/wallpaper/contents/images/`. Run `sudo mv 1920x1080.svg 1920x1080-OLD.svg`, to create a backup of the original image.
Then copy the desired image into the `/usr/share/desktop-base/active-theme/wallpaper/contents/images/`, the command will look something like this `sudo cp ~/Pictures/Wallpapers/<image-name>.png /usr/share/desktop-base/active-theme/wallpaper/contents/images/1920x1080.svg`. Be sure to retain the name `1920x1080.svg` with the new file, even if it isn't an svg file.
