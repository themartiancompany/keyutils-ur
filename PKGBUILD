# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.5.5
pkgrel=2
pkgdesc="Linux Key Management Utilities"
arch=(i686 x86_64)
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=(etc/request-key.conf)
source=(http://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2)
md5sums=('d759680b2f23c99af95938f5026f25fb')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}"
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" LIBDIR="/usr/lib" USRLIBDIR="/usr/lib"  install
}
