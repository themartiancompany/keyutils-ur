# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>
pkgname=keyutils
pkgver=1.5.8
pkgrel=1
pkgdesc="Linux Key Management Utilities"
arch=('i686' 'x86_64')
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=('etc/request-key.conf')
source=(http://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2
        request-key.conf.patch)
md5sums=('3c7f463039b83833c12a9414c2fcb389'
         '89a819a7e4e90936b210c9d5020d296d')

prepare() {
  cd ${pkgname}-${pkgver}
  # fix paths of binaries in /etc/request-key.conf
  patch -Np0 -i ../request-key.conf.patch
}

build() {
  cd ${pkgname}-${pkgver}
  make CFLAGS="${CFLAGS}" LDFLAGS="${LDFLAGS}" SBINDIR='/usr/bin' BINDIR='/usr/bin'
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" SBINDIR='/usr/bin' BINDIR='/usr/bin' LIBDIR='/usr/lib' USRLIBDIR='/usr/lib'  install
}
