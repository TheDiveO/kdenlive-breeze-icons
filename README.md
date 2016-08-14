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
