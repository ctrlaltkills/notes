# SDDM 2
Jump to: [content](#top)

[**Get Gentoo!**](https://get.gentoo.org/)

[gentoo.org sites](#)

*   [gentoo.org](https://www.gentoo.org/ "Main Gentoo website")
*   [Wiki](https://wiki.gentoo.org/ "Find and contribute documentation")
*   [Bugs](https://bugs.gentoo.org/ "Report issues and find common issues")
*   [Forums](https://forums.gentoo.org/ "Discuss with the community")
*   [Packages](https://packages.gentoo.org/ "Find software for your Gentoo")

*   [Planet](https://planet.gentoo.org/ "Find out what's going on in the developer community")
*   [Archives](https://archives.gentoo.org/ "Read up on past discussions")
*   [Gitweb](https://gitweb.gentoo.org/ "Browse our source code in Gitweb")

*   [Infra Status](https://infra-status.gentoo.org/ "Get updates on the services provided by Gentoo")

 [![](https://assets.gentoo.org/tyrian/site-logo.png)](/ "Back to the homepage") Wiki

Toggle navigation

*   [Main page](/wiki/Main_Page "Visit the main page [alt-shift-z]")
*   [Recent changes](/wiki/Special:RecentChanges "A list of recent changes in the wiki [alt-shift-r]")
*   [Help](/wiki/Special:MyLanguage/Help:Contents "The place to find out")
*   [Gentoo](/wiki/Gentoo_Wiki:Menu-Gentoo)
    *   [Gentoo Projects](/wiki/Project:Gentoo)
*   [Documentation](/wiki/Gentoo_Wiki:Menu-Documentation)
    *   [Gentoo Handbook](/wiki/Handbook:Main_Page)
    *   [Gentoo FAQ](/wiki/FAQ)
    *   [Featured Documents](/wiki/Project:Documentation/Overview)
    
    *   Topics
    *   [Core system](/wiki/Category:Core_system)
    *   [Hardware](/wiki/Category:Hardware)
    *   [Software](/wiki/Category:Software)
    *   [Desktop](/wiki/Category:Desktop)
    *   [Server & Security](/wiki/Category:Server_and_Security)
    *   [Project & Community](/wiki/Category:Project_and_Community)

*   [Tools](#)
    *   [What links here](/wiki/Special:WhatLinksHere/SDDM "A list of all wiki pages that link here [alt-shift-j]")
    *   [Related changes](/wiki/Special:RecentChangesLinked/SDDM "Recent changes in pages linked from this page [alt-shift-k]")
    *   [Special pages](/wiki/Special:SpecialPages "A list of all special pages [alt-shift-q]")
    *   [Printable version](javascript:print(); "Printable version of this page [alt-shift-p]")
    *   [Permanent link](/index.php?title=SDDM&oldid=1037075 "Permanent link to this revision of the page")
    *   [Page information](/index.php?title=SDDM&action=info "More information about this page")
    *   [Browse properties](/wiki/Special:Browse/:SDDM)
*   [User](#)
    *   [Create account](/index.php?title=Special:CreateAccount&returnto=SDDM "You are encouraged to create an account and log in; however, it is not mandatory")
    *   [Log in](/index.php?title=Special:UserLogin&returnto=SDDM "You are encouraged to log in; however, it is not mandatory [alt-shift-o]")

Toggle navigation

*   [Page](/wiki/SDDM "View the content page [alt-shift-c]")
*   [Discussion](/wiki/Talk:SDDM "Discussion about the content page [alt-shift-t]")

*   [View source](/index.php?title=SDDM&action=edit "This page is protected.
    You can view its source [alt-shift-e]")
*   [more](#)
    *   [History](/index.php?title=SDDM&action=history "Past revisions of this page [alt-shift-h]")

SDDM
====

From Gentoo Wiki

[Jump to:navigation](#mw-head) [Jump to:search](#searchInput)

**Resources**

[Home](https://github.com/sddm)

[Package information](https://packages.gentoo.org/packages/x11-misc/sddm)

[Wikipedia](https://en.wikipedia.org/wiki/SDDM)

[GitHub](https://github.com/sddm/sddm)

[#sddm](ircs://irc.libera.chat/#sddm) ([webchat](https://web.libera.chat/#sddm))

**S**imple **D**esktop **D**isplay **M**anager (SDDM) is a modern [display manager](/wiki/Display_manager "Display manager") that supports both the X11 server and the Wayland protocol.

**Warning**  
By default, clicking the "power off" icon in SDDM will shut down the machine immediately, without asking for confirmation.

Contents
--------

*   [1 Installation](#Installation)
    *   [1.1 USE flags](#USE_flags)
    *   [1.2 Emerge](#Emerge)
*   [2 Configuration](#Configuration)
    *   [2.1 Files](#Files)
    *   [2.2 Prior to 0.18.0](#Prior_to_0.18.0)
        *   [2.2.1 Keymap](#Keymap)
    *   [2.3 Service](#Service)
        *   [2.3.1 OpenRC](#OpenRC)
            *   [2.3.1.1 With display-manager](#With_display-manager)


Installation
------------

### USE flags

### USE flags for [x11-misc/sddm](https://packages.gentoo.org/packages/x11-misc/sddm) Simple Desktop Display Manager

| `[elogind](https://packages.gentoo.org/useflags/elogind)` | Use sys-auth/elogind for session tracking. |
| `[pam](https://packages.gentoo.org/useflags/pam)` | Add support for PAM (Pluggable Authentication Modules)DANGEROUS to arbitrarily flip |
| `[systemd](https://packages.gentoo.org/useflags/systemd)` | Enable use of systemd-specific libraries and features like socket activation or session tracking |
| `[test](https://packages.gentoo.org/useflags/test)` | Enable dependencies and/or preparations necessary to run tests (usually controlled by FEATURES=test but can be toggled independently) |

Data provided by the [Gentoo Package Database](https://packages.gentoo.org) · Last update: 2017-01-31 11:43 [More information about USE flags](/wiki/Handbook:AMD64/Working/USE)

### Emerge

Install [x11-misc/sddm](https://packages.gentoo.org/packages/x11-misc/sddm):

`root #``emerge --ask x11-misc/sddm`

If there are performance issues, it might help to add the sddm user to the video group:

`root #``usermod -a -G video sddm`

Configuration
-------------

### Files

SDDM has two configuration files: the package installed /usr/share/sddm/sddm.conf.d/00default.conf and /etc/sddm.conf which is used to override specific options. The second is not created by the package. KDE Plasma writes user changed options to /etc/sddm.conf. Both files have the same format. See comments in the file and man 5 sddm.conf for details on available options.

### Prior to 0.18.0

Prior to **0.18.0** the configuration was only in /etc/sddm.conf. Some of the files may have had to be generated manually. If installing **0.18.0**, skip ahead to [Service section](#Service).

#### Keymap

To select the correct keymap on the login screen, add following lines to the /etc/sddm.conf file:

FILE **`/etc/sddm.conf`**

```


\[X11\]
DisplayCommand\=/etc/sddm/scripts/Xsetup





```

This file is not created automatically when the package is installed so it may need to be created.

Next create the directory /etc/sddm/scripts

`root #``mkdir -p /etc/sddm/scripts`

and the file /etc/sddm/scripts/Xsetup.

FILE **`/etc/sddm/scripts/Xsetup`**

```


setxkbmap gb,us





```

the first country code is the default. Finally set execute permissions on the file /etc/sddm/scripts/Xsetup.

`root #``chmod a+x /etc/sddm/scripts/Xsetup`

### Service

#### OpenRC

##### With display-manager

If [gui-libs/display-manager-init](https://packages.gentoo.org/packages/gui-libs/display-manager-init) is not present, emerge it with:

`root #``emerge --ask gui-libs/display-manager-init`

The configuration file should be modified to use SDDM:

FILE **`/etc/conf.d/display-manager`****Set SDDM as the display manager**

```


CHECKVT\=7
DISPLAYMANAGER\="sddm"





```

To start the chosen display manager on boot, add the _display-manager_ to the system's _default_ runlevel:

`root #``rc-update add display-manager default`

To start the _display-manager_ immediately, run:

`root #``rc-service display-manager start`

##### With the deprecated xdm init script

Set SDDM as the default display manager:

FILE **`/etc/conf.d/xdm`**

```


DISPLAYMANAGER\="sddm"





```

To start SDDM on boot, add xdm to the default runlevel:

**Note**  
The dbus service gets pulled in dynamically.

`root #``rc-update add xdm default`

To start SDDM now:

`root #``/etc/init.d/xdm start`

#### systemd

To start SDDM on boot:

`root #``systemctl enable sddm.service`

To start SDDM now:

`root #``systemctl start sddm.service`

### Plasma

Graphical configuration is integrated in Plasma 5 system settings by installing [kde-plasma/sddm-kcm](https://packages.gentoo.org/packages/kde-plasma/sddm-kcm):

`root #``emerge --ask kde-plasma/sddm-kcm`

Troubleshooting
---------------

### Long load time before SDDM shows the greeter

A low entropy pool can cause long SDDM load time - see [upstream bug report](https://github.com/sddm/sddm/issues/1036). If using systemd, the graphical target is reached and then everything appears to hang. Moving the mouse or using the keyboard will make the SDDM greeter launch (faster).

Solve the problem by using, for example, the [sys-apps/haveged](https://packages.gentoo.org/packages/sys-apps/haveged) package to increase the entropy pool or by enabling RANDOM\_TRUST\_CPU kernel config option [with a recent-enough CPU](https://en.wikipedia.org/wiki/RdRand "wikipedia:RdRand").

### Permission denied errors in Xorg.log

The X server will not start and permission denied errors (such as the following) are present in the Xorg.log log file:

FILE **`/var/log/Xorg.log`**

```


/var/log/Xorg.0.log:\[ 2058.998\] (EE) /dev/dri/card0: failed to set DRM interface version 1.4: Permission denied
/var/log/Xorg.0.log:\[ 2061.229\] (EE) intel(0): \[drm\] failed to set drm interface version: Permission denied \[13\].





```

It is likely the sddm user has not been added to the video group. Running the following command should fix the problem:

`root #``usermod -a -G video sddm`

### Missing system buttons

SDDM only displays buttons if the functionality evaluates to being available. This can depend on several factors. For OpenRC systems using elogind, this can be caused by the service not running when the display manager is initialized. To make sure it is running, just add elogind to the boot run level.

`root #``rc-update add elogind boot`

### Missing users

If the login screen is missing some user(s) to choose from, this might be caused by /etc/sddm.conf - standard `MinimumUid` is 1000 and some existing users may have lower uids.

FILE **`/etc/sddm.conf`**

```


\[Users\]
MaximumUid\=60000
MinimumUid\=1000





```

### SDDM service starts but yields a black screen

On NVIDIA cards, SDDM appears to require DRM enabled and operational according to [this closed bug report](https://bugs.gentoo.org/697634).

Ensure Direct Rendering Manager is enabled in the kernel. If it isn't, enable it, rebuild the kernel, and re-emerge nvidia-drivers.

KERNEL **Enable Direct Rendering Manager**

```
Device Drivers --->
    Graphics support --->
        <\*> Direct Rendering Manager (XFree86 4.1.0 and higher DRI support) --->
            \[\*\] Enable legacy fbdev support for your modesetting driver
```

Ensure the nvidia-drm module is configured to load at startup:

FILE **`/etc/modules-load.d/nvidia-drm.conf`**

```
nvidia-drm
```

Finally, ensure nvidia-drm has modesetting enabled:

FILE **`/etc/modprobe.d/nvidia-drm.conf`**

```
options nvidia-drm modeset=1
```

Alternatively, modesetting can be enabled on the kernel command line with nvidia-drm.modeset=1. This can be set in the bootloader or embedded in the kernel configuration.
