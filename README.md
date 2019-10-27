# xsession-gnome-flashback

Gnome-flashback support for .xsession

## What is it not?

You probably want [xsession-gnome](https://github.com/bugi/xsession-gnome)
instead.  Flashback provides a panel, notifier, and other stuff that you
probably don't want if you're using a .xsession file.

This use of gnome-flashback doesn't work for me with Ubuntu 19.10 (PopOs
variant).  Please submit a pull request if you get it working.

I am taking pull requests, but have otherwise stopped maintaining this
software.

## What is it?

xsession-gnome-flashback provides scaffolding to help you run your normal
window manager within a Gnome session.

A Gnome session provides desktop features like managing some or all of your
wifi, bluetooth, displays, keyboards, and mice.

After setting up the Gnome session, your .xsession file takes over
and you can run any window manager you like.

## Why?

Why do it this way?  In my case I want to use a window manager that I
can optimize to fit my workflow.  At the same time, I also don't want to
disrupt my workflow to deal with the arcana of setting up wifi manually.  I
get control where I want it, but I can let Gnome handle the parts I don't
want to handle.

Why not just use [Gnome Flashback](https://wiki.gnome.org/Projects/GnomeFlashback)
directly?  Or [Regolith Linux](http://regolith-linux.org/)?
Those and others are specific to a given window manager.  This general
solution enables myself and others to customize as we please, including
using other window managers like
[i3](https://i3wm.org/) or [vtwm](http://www.vtwm.org/)

## Orientation for Baffled

If none of the above made sense to you
but you want to learn more, peruse
[i3](https://i3wm.org/)'s
[collection of videos and screenshots](https://i3wm.org/screenshots/)
to get some idea of what it can be like to step outside Gnome or KDE.

I mentioned i3 and vtwm above.  Those are two window managers
especially dear to my heart, and provide an illustrative contrast.
I3 helps you organize your workspace structurally,
while vtwm lets you organize your workspace spatially by providing a
near-infinite virtual desktop.

Many other window managers exist as well, usually falling somewhere
between i3's and vtwm's workspace management styles.


# Installation

## Install Prerequisites

Assuming Debian or Ubuntu, install the prerequisites:

```
sudo apt update
sudo apt install gnome-session-flashback
```


## Install Display Manager and Session Manager Files

In order to run a .xsession file within Gnome-Flashback, you will
need to select the option from your display manager.  To provide
that option, install several files.

```
sudo ./INSTALL
```


## Install Your .xsession-gnome File

Provided is a file `dot.xsession-gnome`.  It demonstrates a minimal
`~/.xsession-gnome` file.  That example being so minimal, I recommend you
copy your existing .xsession file to .xsession-gnome and pare that down to
minimize overlap with the services that Gnome provides.

The provided session manager startup scaffolding will first try
to run a `~/.xsession-gnome` file.  If that is not available, it
will try to run a `~/.xsession` file.  If that is also not available,
it will try to run `i3`.  Failing that, login will fail and you will
find yourself confused and you should reread this document from
the beginning.


# Thanks

My most immediate inspiration was [Regolith Linux](http://regolith-linux.org/).
Regolith's release inspired me to finish, clean up, and package
my tools for general consumption.  Regolith's
files were also cleaner and better organized than mine were,
so I rebased mine from the
[regolith-gnome-flashback](https://github.com/regolith-linux/regolith-gnome-flashback)
part of Regolith.

Some other inspirations included:
* https://wiki.archlinux.org/index.php/GNOME/Flashback
* https://wiki.gnome.org/Projects/GnomeFlashback
* http://zork.net/~st/jottings/gnome-i3.html



# Usage tips

## Adjusting Gnome Settings

To adjust Gnome's settings, you will likely want to launch
Gnome's Settings application.

Because traditional window managers often provide no mechanism for
launching Gnome's Settings application, you may want
to install something that provides said functionality,
like [rofi](https://github.com/davatorium/rofi).

To install rofi:

```
sudo apt install rofi
```

To run rofi from the commandline:

```
rofi -modi drun -show drun
```

