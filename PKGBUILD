# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-activities
pkgver=6.6.5
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=2
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
sha256sums=('5d254c690c21da39f958a2ec8071706a30e1ab070e2080263622170e8ac5bd88')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
