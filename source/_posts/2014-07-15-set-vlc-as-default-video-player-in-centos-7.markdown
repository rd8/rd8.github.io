---
layout: post
title: "Set VLC as default video player in CentOS 7"
date: 2014-07-15 21:34:16 -0500
comments: true
categories:
---

It took a while to build VLC player from git source under new CentOS 7.

Theoretically you should only install those packages marked with el7, but some packages with el6 are only available for the time being, and they are needed in compiling other packages. Another thing is, even if you have installed an el7 version of some package, like aalib, when you do yum update, it asks you to update to its el6 version, which would definitely fail.

There are several repos helped me a bit with it:

1. base: mirrors.easynews.com
2. epel: mirror.utexas.edu
3. extras: mirror.anl.gov
4. linuxtech-release: pkgrepo.linuxtech.net
5. nux-dextop: mirror.li.nux.ro
6. rpmforge: mirror.team-cymru.org
7. rpmfusion-free-updates: mirror.nexcess.net
8. updates: centosi3.centos.org

It's helpful to use yum whatprovides <lib file name> to check what packages provide a specified lib file. Most of the time, the dependencies are installed one by one. --skip-broken can help a bit in batch install, but it is still clearer to solve dependencies in steps.

Ok, the short version of the long story is, VLC can be installed after ffmpeg and several other important packages have been installed in CentOS 7. And, the more important thing is, hardware acceleration can be enabled if you are using Intel Sandy Bridge CPU like i3, i5. Maybe another post would be good to address this, because it is the key to get better performance for a modern video player.

My recent but not last annoyance in VLC under CentOS 7 is, it is not shown in the list of applications when you click a video file.

<p align='center'>
<img src="{{ root_url }}/images/posts/2014-07-15-open-with-other-apps.png" />
</p>

It is not so easy to make VLC appear in this list, but I happened to find a dummy way to do this, and even better:

<img src="{{ root_url }}/images/posts/2014-07-15-set-vlc-as-default.png" />

This terminated my pain. Now VLC is the best video player in my CentOS box, kicking XBMC to be the choice only for LAN video playing.
