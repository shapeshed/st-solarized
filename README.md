# st-solarized

An ArchLinux PKGBUILD for [st][1] with patches applied for the [Solarized][2] theme.

## Installation

    cowerd st-solarized
    cd src
    makepkg -sri

## Setting a font

A custom font may be set using the `-f` option.

    st -f Inconsolata:pixelsize=20:antialias=true:autohint=true

If this is tedious to type every time create an alias

    alias st='st -f Inconsolata:pixelsize=20:antialias=true:autohint=true'

## Usage

Refer to the [Arch Linux Wiki][3] for usage.

[1]: http://st.suckless.org/
[2]: http://ethanschoonover.com/solarized
[3]: https://wiki.archlinux.org/index.php/st

