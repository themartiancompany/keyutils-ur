# Maintainer: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.5.5
pkgrel=1
pkgdesc="Linux Key Management Utilities"
arch=(i686 x86_64)
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=(etc/request-key.conf)
source=(http://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2)
md5sums=('9e8ab5164bc8f84be148761cc89e9d6f')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i "s|/lib64|/lib|g" Makefile
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}"
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
