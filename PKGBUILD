# Maintainer: acxz <akashpatel2008 at yahoo dot com>
# Contributor: Tim Rakowski <tim.rakowski@gmail.com>

pkgname=ignition-cmake
pkgver=2.12.1
pkgrel=1
pkgdesc="Provides modules that are used to find dependencies of ignition projects and generate cmake targets for consumers of ignition projects to link against."
arch=('any')
url="https://ignitionrobotics.org/libs/cmake"
license=('Apache')
groups=('development')
depends=('cmake' 'pkg-config' 'ruby-ronn' 'doxygen')
optdepends=()
conflicts=()
source=("https://github.com/ignitionrobotics/ign-cmake/archive/${pkgname}2_${pkgver}.tar.gz")
sha256sums=('9f577844579e679f39c140f74a9f7688d552959688cefc7ddeb72dd7bf86f7ac')

_dir="ign-cmake-${pkgname}2_${pkgver}"

build() {
  cd "$srcdir/$_dir"

  mkdir -p build
  cd build

  # Configure build
  cmake .. -Wno-dev \
           -DCMAKE_BUILD_TYPE="Release" \
           -DCMAKE_INSTALL_PREFIX="${pkgdir}/usr" \
           -DCMAKE_INSTALL_LIBDIR="lib" \
           -DBUILD_TESTING=OFF

  # Compile
  make
}

package() {
  cd "$srcdir/$_dir/build"
  #make DESTDIR="$pkgdir/" install
  make install
}
