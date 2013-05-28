# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.5.5
pkgrel=5
pkgdesc="Linux Key Management Utilities"
arch=(i686 x86_64)
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=(etc/request-key.conf)
source=(http://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2
request-key.conf.patch)
md5sums=('d759680b2f23c99af95938f5026f25fb'
         '89a819a7e4e90936b210c9d5020d296d')

prepare() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  # fix paths of binaries in /etc/request-key.conf
  patch -Np0 -i ../request-key.conf.patch
}

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}" SBINDIR='/usr/bin' BINDIR='/usr/bin'
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" SBINDIR='/usr/bin' BINDIR='/usr/bin' LIBDIR='/usr/lib' USRLIBDIR='/usr/lib'  install
}
