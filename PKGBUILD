# Maintainer: Manuel Schneider  <manuelschneid3r at googles mail>
pkgname=albert
pkgver=0.8.7.2
pkgrel=1
pkgdesc="A DE agnostic omnilauncher."
arch=('i686' 'x86_64')
url="https://github.com/ManuelSchneid3r/albert"
license=('GPL')
depends=('qt5-base' 'libx11' 'muparser' 'qt5-x11extras' 'qt5-svg')
makedepends=('cmake' 'qt5-base' 'qt5-tools')
provides=('albert')
conflicts=('albert-git')
source=(https://github.com/ManuelSchneid3r/albert/archive/v${pkgver}.tar.gz)
noextract=()
md5sums=('0a983951de8b4ef3c8a95d018b57fb7b')

build() {
  [[ -d "${pkgname}-${pkgver}/build" ]]\
    || mkdir -p "${pkgname}-${pkgver}/build"
  cd "${pkgname}-${pkgver}/build"
  cmake ".." \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Debug
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
