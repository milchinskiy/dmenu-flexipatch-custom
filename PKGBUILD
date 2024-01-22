# Maintainer: Alexander Milchinskiy <milchinskiy@gmail.com>

pkgname=dmenu-flexipatch
pkgver=5.2
pkgrel=5
pkgdesc="dmenu is a dynamic menu for X, originally designed for dwm"
url="https://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxft' 'libxinerama' 'sh' 'freetype2')

prepare() {
  cd ..
  make clean
  rm -f config.h patches.h
}

build() {
  cd ..
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd ..
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname"/LICENSE
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname"/README
}
