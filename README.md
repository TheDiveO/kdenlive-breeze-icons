[![LGPL](https://img.shields.io/badge/license-LGPL%20License-blue.svg)](COPYING-ICONS) [![Kdenlive](https://img.shields.io/badge/nle-Kdenlive-brightgreen.svg)](https://www.kdenlive.org) [![KF5](https://img.shields.io/badge/desktop-KF5-green.svg)](https://www.kde.org)

# Kdenlive Breeze Icons

The Kdenlive-specific Breeze icons. Stylable, so they adapt to the particular color theme in use.

The Kdenlive Breeze icons base on the famous (Breeze icon set)[https://github.com/KDE/breeze-icons] (GitHub). Please note that this repository contains only those icons specific to Kdenlive. It mainly serves as a development place for these icons until they find their way into the original Breeze icon set.

This repository is especially useful when you:

1. compile Kdenlive yourself,
2. _and_ install it into some other place than a system-wide location, such as inside your `$HOME`.
 
Unfortunately, with this setup, any updated Kdenlive icons installed into your local install will simply be ignored. Only new icons will be picked up. The reason for this unexpected and undesired behavior are hidden deep inside the (KF5) mechanics of icon handling. The only way at this time is to also clone the Breeze icon set into your `$HOME` and then update this local set with the more recent Kdenlive icons. Not exactly beautiful, but at least this method works.

# Installation

In order to use Kdenlive's updated color theme-adaptive Breeze icons, we basically first need to set up a local copy of the original Breeze icon theme. The reason is that for updating some icons, the theme inheritance mechanism of KF5 doesn't work as required. So we need a full copy. Next, we then update the old or add the missing Kdenlive adaptive icons.

1. create `$HOME/local/share/icons` &ndash; this will next receive our local copy of the Breeze icon set. Unfortunately, there's no way making a local copy and then updating the required Kdenlive icons. 
2. copy the complete stock Breeze icon theme from `/usr/share/icons/breeze` into `$HOME/local/share/icons/breeze`
3. copy the icons from this repository into `$HOME/locals/share/icons/breeze`, updating the Kdenlive-specific icons.
4. remove `$HOME/.cache/icon-cache.kcache` to be on the safe side; this removes all potentially cached and now stale Breeze icons from the cache, so the updated icons will be used instead (and cached now).
5. as with any local Kdenlive install outside the system directories, make sure that `XDG_DATA_DIRS` correctly points to your local stuff; that is, to `$HOME/local/share`. Failing to do so will Kdenlive not let see and use the updated Breeze icon set.
6. make sure that you've selected the Breeze icon set (and not Breeze dark or some other icon set).

# Notes

Currently, when Kdenlive is installed into a local folder, then its icons get copied into the fall-back `hicolor` icon set. This is flawed in several points:

1. this local branch has no `index.theme`, so it's not even a real icon theme.
2. this local icon set is not complete; so when you try to force Kdenlive/KF5 to use only your local `hicolor` icon theme, many icons will be missing.
3. last, but not least, without an `index.theme` there is no `FollowsColorScheme=true` indication that tells KF5 that it can theme this particular icon set.

# License

The license for Kdenlive's Breeze icons is the same as for the original Breeze icons: [LGPL](COPYING.LIB) with an [explicit clarification that these icons are covered by the LGPL](COPYING-ICONS).

# References

It took me quite some time to figure out the whole CSS styled icons stuff in its details, because the information is mostly scattered around different blog posts. As usual, the final say has the source code, so I've included the interesting module below in my references. This way, others don't need to duplicate my search efforts. Enjoy!

* [Theme details: Using system colors](https://techbase.kde.org/Development/Tutorials/Plasma4/ThemeDetails#Using_system_colors) &ndash; probably the most important document with respect to theming Breeze (and other) icon sets; in particular, this document lists the available CSS classes that KF5 supports for themed icons, yet it is incomplete. Luckily, with the help of [kiconloader.cpp](https://github.com/KDE/kiconthemes/blob/master/src/kiconloader.cpp) (see `STYLESHEET_TEMPLATE`) we can construct a complete list of these six classes:
  * ![ColorScheme-Text](https://img.shields.io/badge/class-ColorScheme--Text-4d4d4d.svg) `ColorScheme-Text` (#4d4d4d) &ndash; probably the most useful of all theming classes: use for painting all normal icon elements.
  * ![ColorScheme-Highlight](https://img.shields.io/badge/class-ColorScheme--Highlight-3daee9.svg) `ColorScheme-Highlight` (#3daee9) &ndash; highlight (contrast) color.
  * ![ColorScheme-Background](https://img.shields.io/badge/class-ColorScheme--Background-eff0f1.svg) `ColorScheme-Background` (#eff0f1) &ndash; background color; usually you should not need it, as any decent SVG editor (such as [Inkscape](https://www.inkscape.org)) offers tools to cut out regions so that the background becomes visible.
  * ![ColorScheme-PositiveText](https://img.shields.io/badge/class-ColorScheme--PositiveText-2ecc71.svg) `ColorScheme-PositiveText` (#2ecc71) &ndash; can be used for new/add operations ... but be careful, as the current Breeze icon design these days usually stays with `ColorScheme-Text` instead.
  * ![ColorScheme-NeutralText](https://img.shields.io/badge/class-ColorScheme--NeutralText-f67400.svg) `ColorScheme-NeutralText` (#f67400) &ndash; useful for accentuation, where `ColorScheme-Highlight` isn't desired. Use with great care, though.
  * ![ColorScheme-NegativeText](https://img.shields.io/badge/class-ColorScheme--NegativeText-da4453.svg) `ColorScheme-NegativeText` (#da4453) &ndash; use for remove operations, et cetera.
* [kiconloader.cpp](https://github.com/KDE/kiconthemes/blob/master/src/kiconloader.cpp) does the necessary CSS style adaption, see here:
  * `STYLESHEET_TEMPLATE` &ndash; defines the SVG CSS template.
  * `KIconLoaderPrivate::processSvg` &ndash; does the magic: it replaces the CSS `<style>` with `id="current-color-scheme"` with the `STYLESHEET_TEMPLATE`, inserting the current color theme values for the (six) CSS classes listed above.
* KDE Visual Design Group/HIG:
  * [Color](https://community.kde.org/KDE_Visual_Design_Group/HIG/Color) &ndash; the Breeze color theme and color roles. Of particular use are these colors (use the CSS style class names, as listed above, instead of hard-coded RGB values):
    * ![Icon Grey](https://img.shields.io/badge/color-Icon%20Grey-4d4d4d.svg) Icon Grey: #4d4d4d
    * ![Plasma Blue](https://img.shields.io/badge/color-Plasma%20Blue-3daee9.svg) Plasma Blue: #3daee9
    * ![Cardboard Grey](https://img.shields.io/badge/color-Cardboard%20Grey-eff0f1.svg) Cardboard Grey: #eff0f1
    * ![Icon Red](https://img.shields.io/badge/color-Icon%20Red-da4453.svg) Icon Red: #da4453
    * ![Icon Green](https://img.shields.io/badge/color-Icon%20Green-2ecc71.svg) Icon Green: #2ecc71
    * ![Beware Orange](https://img.shields.io/badge/color-Beware%20Orage-f67400.svg) Beware Orange: #f67400
  * [Icon Design](https://community.kde.org/KDE_Visual_Design_Group/HIG/IconDesign) &ndash; Breeze icon design with respect to color, sizes, et cetera.
* [Performance updates for breeze icons](https://kdeonlinux.wordpress.com/2016/04/25/performance-update-for-breeze-icons/) &ndash; overall info about Breeze icon styling.

Note: example color codes and patches are for Breeze (Light).
