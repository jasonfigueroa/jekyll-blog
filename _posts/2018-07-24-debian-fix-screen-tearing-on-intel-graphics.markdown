---
layout: post
title:  "Debian Fix Screen Tearing on Intel Graphics"
date:   2018-07-22 19:18:00 -0500
categories: linux debian
---
The following worked for me on a Debian 9.4 install on my Dell laptop. The processor in the laptop is an Intel i5-4200u. 

Reference: [How to Fix Linux screen tearing on Intel graphics][how-to-fix-linux-screen-tearing-on-intel-graphics]

[how-to-fix-linux-screen-tearing-on-intel-graphics]: https://www.pcsuggest.com/fix-linux-screen-tearing/

Make sure `/etc/X11/xorg.conf.d` exists. If it doesn't, in the terminal, run `mkdir -p /etc/X11/xorg.conf.d`. If your system complains about permissions prepend the preceding command with `sudo`.

Cd into `/etc/X11/xorg.conf.d`. Then run `touch 20-intel.conf` and open that file in a text editor and add the following:

{% highlight bash %}
Section "Device"
  Identifier "Intel Graphics"
  Driver "intel"
  Option "TearFree" "true"
EndSection
{% endhighlight %}

Reboot your system.

