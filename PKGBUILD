# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kross
pkgver=4.99.0
pkgrel=1
pkgdesc='Kross'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kross'
license=('LGPL')
depends=('kparts')
makedepends=('extra-cmake-modules' 'kdoctools' 'qt5-tools')
groups=('kf5-aids')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/portingAids/${pkgname}-${pkgver}.tar.xz")
md5sums=('507123a1180905e23b8deb3c9988026b')

prepare() {
  mkdir -p build
}

build() {
  export XDG_DATA_DIRS="/opt/kf5/share:$XDG_DATA_DIRS"

  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
