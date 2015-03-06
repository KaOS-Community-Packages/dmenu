pkgname=dmenu
pkgver=4.5.13.5ed5e90
pkgrel=1
pkgdesc="A generic menu for X"
url="http://tools.suckless.org/dmenu/"
arch=('x86_64')
license=('MIT')
depends=('sh' 'libxinerama')
makedepends=('git')
source=(git://git.suckless.org/dmenu#commit=5ed5e90bf)
md5sums=('SKIP')

pkgver() {
  cd $pkgname
  echo 4.5.$(git rev-list 7f45b3f7a..@ --count).$(git rev-parse --short HEAD)
}

build(){
  cd $pkgname
  make \
    X11INC=/usr/include/X11 \
    X11LIB=/usr/lib/X11
}

package() {
  cd $pkgname
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
