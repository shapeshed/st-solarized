# Maintainer: George Ornbo <george@shapeshed.com>
# Source: https://github.com/shapeshed/st-solarized-dark

pkgname=st-solarized
appname='st'
provides=('st')
conflicts=('st')
pkgver=0.8
pkgrel=1
pkgdesc='A simple virtual terminal emulator for X. Patched for solarized dark and Inconsolata font.'
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxext' 'libxft')
makedepends=('ncurses')
url="http://st.suckless.org"
source=('git://git.suckless.org/st#commit=b331da550b290d54592b7ba11242c92f5a303a48'
        'http://st.suckless.org/patches/solarized/st-no_bold_colors-20170623-b331da5.diff'  
        'http://st.suckless.org/patches/solarized/st-solarized-both-20170626-b331da5.diff')

sha256sums=('SKIP'
        '71e1211189d9e11da93ee49388379c5f8469fcd3e1f48bb4d791ddaf161f5845'
        'd1f168d225763680c6dc6e9a426b8bb56ff45967ffd0ea79f56b7af42c1141d9')

prepare() {
  cd "$srcdir/$appname"
  patch -i "$srcdir/st-no_bold_colors-20170623-b331da5.diff"
  patch -i "$srcdir/st-solarized-both-20170626-b331da5.diff"
  cp config.def.h config.h
  sed -i 's/Liberation Mono:pixelsize=12:antialias=true:autohint=true/Inconsolata:pixelsize=20:antialias=true:autohint=true/' config.h 
}

build() {
  cd "$srcdir/$appname"
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd "$srcdir/$appname"
  make PREFIX=/usr DESTDIR="$pkgdir" TERMINFO="$pkgdir/usr/share/terminfo" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
}
