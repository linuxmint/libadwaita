This is the patched version of libAdwaita in Mint 23.

It is based on libAdwaita 1.9 and adds theme support.

CSS support
-----------

The library uses the current GTK3 theme. If it provides a `libadwaita-1.9` directory, it uses the theme's stylesheet. Otherwise it falls back to the library's own stylesheet, which looks exactly the same as upstream libadwaita.

Inside the theme's `libadwaita-1.9` directory, there should be:

- `gtk.css` — the full stylesheet (it is a single file in 1.9; light/dark and high-contrast variants are selected by GTK at runtime via `prefers-color-scheme` / `prefers-contrast` `@media` queries inside this file)
- `assets/` — pictures used by the stylesheet

You can find an example installed at `/usr/share/themes/LibAdwaita-Example/libadwaita-1.9` after installing the `libadwaita-1-examples` package.

To minimize potential issues it is recommended to only change the colors and the style of the window controls.

SASS support
------------

If your theme uses SASS you can work from the SASS files directly and get greater control. The stylesheet sources are in the `src/stylesheet` directory.

Examples
--------

Mint-X and Mint-Y implement support for this library. You can find their stylesheets in `/usr/share/themes/Mint-X/libadwaita-1.9` and `/usr/share/themes/Mint-Y/libadwaita-1.9`, or on github at https://github.com/linuxmint/mint-themes/tree/master/files/usr/share/themes.
