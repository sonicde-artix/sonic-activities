# Maintainer: artist for Artix Linux

pkgname=sonic-activities
pkgver=6.6.5
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
_commit="144e52b0a5c48b367bbcee87f126fd6cdd3d308e"
pkgdesc='Core components for SonicDE Activities'
arch=(x86_64)
url="https://github.com/Sonic-DE/$pkgname"
license=(LGPL-2.0-or-later)
depends=(glibc
         kconfig
         sonic-frameworks-core-addons
         libgcc
         qt6-base)
makedepends=(extra-cmake-modules
             qt6-declarative
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
conflicts=(kactivities plasma-activities)
replaces=(kactivities plasma-activities)
provides=(plasma-activities)
groups=(sonicde)
makedepends+=(git)
source=("$pkgname-$pkgver::git+$url.git#commit=$_commit")

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
sha256sums=('caaceb5f1bba5d5e6c93a1a6948e55730a0ff9cfc7558f552739272fb1eb010b')
