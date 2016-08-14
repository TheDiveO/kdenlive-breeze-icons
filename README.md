[![LGPL](https://img.shields.io/badge/license-LGPL%20License-blue.svg)](COPYING-ICONS) [![Kdenlive](https://img.shields.io/badge/NLE-Kdenlive-brightgreen.svg)](https://www.kdenlive.org) [![KF5](https://img.shields.io/badge/desktop-KF5-green.svg)](https://www.kde.org)

# Kdenlive Breeze Icons

The Kdenlive-specific Breeze icons. Stylable, so they adapt to the particular color theme in use.

The Kdenlive Breeze icons base on the famous (Breeze icon set)[https://github.com/KDE/breeze-icons] (GitHub). Please note that this repository contains only those icons specific to Kdenlive. It mainly serves as a development place for these icons until they find their way into the original Breeze icon set.

This repository is especially useful when you:

1. compile Kdenlive yourself,
2. _and_ install it into some other place than a system-wide location, such as inside your `$HOME`.
 
Unfortunately, with this setup, any updated Kdenlive icons installed into your local install will simply be ignored. Only new icons will be picked up. The reason for this unexpected and undesired behavior are hidden deep inside the (KF5) mechanics of icon handling. The only way at this time is to also clone the Breeze icon set into your `$HOME` and then update this local set with the more recent Kdenlive icons. Not exactly beautiful, but at least this method works.

# Installation

(to be written)

# License

The license for Kdenlive's Breeze icons is the same as for the original Breeze icons: [LGPL](COPYING.LIB) with an [explicit clarification that these icons are covered by the LGPL](COPYING-ICONS).

# References

* [Theme details: Using system colors](https://techbase.kde.org/Development/Tutorials/Plasma4/ThemeDetails#Using_system_colors) -- probably the most important document with respect to theming Breeze (and other) icon sets; in particular, this document lists the available CSS classes that KF5 supports for themed icons:
  * ![ColorScheme-Text](https://img.shields.io/badge/color-ColorScheme--Text-4d4d4d.svg) `ColorScheme-Text` (#4d4d4d) -- probably the most useful of all theming classes: use for painting all normal icon elements.
  * ![ColorScheme-Highlight](https://img.shields.io/badge/color-ColorScheme--Highlight-3daee9.svg) `ColorScheme-Highlight` (#3daee9) -- highlight (contrast) color.
  * ...
* KDE Visual Design Group/HIG:
  * [Color](https://community.kde.org/KDE_Visual_Design_Group/HIG/Color) -- the Breeze color theme and color roles. Of particular use:
    * ![icon red](https://img.shields.io/badge/color-icon%20red-da4453.svg) icon red: #da4453
    * ![icon green](https://img.shields.io/badge/color-icon%20green-2ecc71.svg) icon green: #2ecc71
  * [Icon Design](https://community.kde.org/KDE_Visual_Design_Group/HIG/IconDesign) -- Breeze icon design with respect to color, sizes, et cetera.
* [Performance updates for breeze icons](https://kdeonlinux.wordpress.com/2016/04/25/performance-update-for-breeze-icons/) -- overall info about Breeze icon styling.
