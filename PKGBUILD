# Maintainer: David Spicer <azleifel at gmail dot com>

pkgname=vdr-dvbapi-git
_gitname=vdr-plugin-dvbapi
pkgver=20140522
pkgrel=1
pkgdesc="A VDR plugin that acts as a bridge between VDR and OScam"
arch=('i686' 'x86_64')
url="https://github.com/manio/vdr-plugin-dvbapi"
license=('GPL2')
depends=('vdr>=2.1.3')
makedepends=('git')
provides=('vdr-dvbapi')
conflicts=('vdr-dvbapi')
source=('git+https://github.com/manio/vdr-plugin-dvbapi.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  git log -1 --format="%cd" --date=short | sed 's|-||g'
}

build() {
  cd "$srcdir/$_gitname"

  make
}

package() {
  cd "$srcdir/$_gitname"

  make DESTDIR="$pkgdir/" install

  # Install documents
  install -d -m755 "$pkgdir/usr/share/doc/$pkgname"
  install -m644 FAQ "$pkgdir/usr/share/doc/$pkgname"
  install -m644 README "$pkgdir/usr/share/doc/$pkgname"
}
