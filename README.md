higon's Portage Overlay
=======================

higon's portage overlay is a custom ebuild package tree for my Funtoo / Gentoo boxes.
Tested on x86/amd64 junk PCs and virtual machines.

Packages
-----------

* dev-util/eclipse-sdk-bin

   Eclipse Kepler (4.3) binary installation.

* x11-apps/ttmkfdir

   TrueType fonts utility.
   Required by 'x11-apps/xfs' package.

* x11-apps/xfs

   Newer X Window Font Server which ebuild was removed from the official portage.



Installation
------------

Add a local repository.
 
> mkdir -p /usr/local/portage
> cd /usr/local/portage
> git clone git://github.com/hyamamoto/portage-higon.git /usr/local/portage/higon
> vi /etc/make.conf

then add a following line like...

> PORTDIR_OVERLAY="/usr/local/portage/higon"


Installation using Layman
--------------------------

(1) install layman
> emerge layman
> echo 'source /usr/local/portage/layman/make.conf" >> /etc/make.conf
(2) Add URL for metadata XML 
> https://raw.github.com/hyamamoto/portage-higon/master/metadata/higon.xml
(3) Just add it to laymen's 'overlays' section Then 
> layman -a higon
(4) Then 
* To sync individually:
> layman -s
* To sync all: 
> layman -S

Misc
----

Files in this portage is _Distributed under the terms of the GNU General Public License v2_

If you have any problem, please report them to Hiroshi Yamamoto (higon at freepress.jp)
