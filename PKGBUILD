# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>

pkgname=keyutils
pkgver=1.5.10
pkgrel=2
pkgdesc="Linux Key Management Utilities"
arch=('x86_64')
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=('etc/request-key.conf')
source=(https://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2
        request-key.conf.patch)
sha256sums=('115c3deae7f181778fd0e0ffaa2dad1bf1fe2f5677cf2e0e348cdb7a1c93afb6'
            '203c602c61ed94ccd423a0a453d74143d678c641a9a4486367576ee8af2cb8d6')

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
  make DESTDIR="${pkgdir}" SBINDIR='/usr/bin' BINDIR='/usr/bin' LIBDIR='/usr/lib' USRLIBDIR='/usr/lib' install
}
