# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.4
pkgrel=1
pkgdesc="Linux Key Management Utilities"
arch=(i686 x86_64)
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=(etc/request-key.conf)
source=(http://people.redhat.com/~dhowells/$pkgname/$pkgname-$pkgver.tar.bz2)

build() {
  cd "$srcdir/$pkgname-$pkgver"
  sed -i -e '/CFLAGS/s|:= -g -O2|+=|' Makefile
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}"
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
md5sums=('e168c1bdaf5aa93c2cbf8a5e7f8ef27b')
