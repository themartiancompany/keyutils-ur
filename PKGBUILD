# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>

pkgname=keyutils
pkgver=1.5.11
pkgrel=1
pkgdesc="Linux Key Management Utilities"
arch=('x86_64')
url="http://www.kernel.org"
license=('GPL2' 'LGPL2.1')
depends=('glibc' 'sh')
backup=('etc/request-key.conf')
validpgpkeys=('A86E54B0D5E1B4E0AB7C640FFBB7576BA7CB0B6B') # David Howells <dhowells@redhat.com>
source=("https://people.redhat.com/~dhowells/${pkgname}/${pkgname}-${pkgver}.tar.bz2"{,.sig}
        'request-key.conf.patch')
sha256sums=('11584488206edc30736263eb855bf7793f16e661987241d333d3cb5ea479b1b5'
            'SKIP'
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
