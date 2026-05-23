# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-activities
pkgver=6.6.5
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
pkgdesc='Core components for SonicDE Activities'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-activities'
license=(LGPL-2.0-or-later)
depends=(glibc
         kconfig
         libgcc
         qt6-base
         sonic-frameworks-core-addons)
makedepends=(extra-cmake-modules
             qt6-declarative
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
groups=(sonicde)
conflicts=(kactivities plasma-activities)
replaces=(kactivities plasma-activities)
provides=(plasma-activities)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('caaceb5f1bba5d5e6c93a1a6948e55730a0ff9cfc7558f552739272fb1eb010b')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
