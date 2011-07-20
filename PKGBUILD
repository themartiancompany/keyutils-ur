# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.5.1
pkgrel=1
pkgdesc="Linux Key Management Utilities"
arch=(i686 x86_64)
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=(etc/request-key.conf)
source=(http://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2)

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i "s|/lib64|/lib|g" Makefile
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}"
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
md5sums=('3ab62455a37a20f73b2d6cc794aaba13')
