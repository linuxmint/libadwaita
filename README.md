This is the patched version of libAdwaita in LMDE 7.

It is based on libAdwaita 1.7 and adds theme support.

CSS support
-----------

The library uses the current GTK3 theme. If it provides a `libadwaita-1.7` directory, it uses the theme's stylesheets. Otherwise it fallsback to the library's own stylesheet, which looks exactly the same as upstream libadwaita.

Inside the theme's `libadwaita-1.7` directory, there should be the following CSS files:

- `defaults-light.css` defines the colors in Light mode
- `defaults-dark.css` defines the colors in dark mode
- `base.css` defines the widgets style
- `base-hc.css` defines the widgets style in high-contrast mode
- `assets` provide pictures used by the stylesheet

You can find these files in `/usr/share/themes/LibAdwaita-Example/libadwaita-1.7` after installing the `libadwaita-1-examples` package.

To minimize potential issues it is recommended to only change the colors and the style of the window controls.

The best place to modify the window controls is at the bottom of `base.css`.

SASS support
------------

If your theme uses SASS you can work from the SASS files directly and get greater control.

In this case, you can find the stylesheet here in the `src/stylesheet` directory.

Examples
--------

Mint-X and Mint-Y implement support for this library.

You can find their stylesheets in `/usr/share/themes/Mint-X/libadwaita-1.7` and `/usr/share/themes/Mint-Y/libadwaita-1.7`, or on github at https://github.com/linuxmint/mint-themes/tree/master/files/usr/share/themes.

