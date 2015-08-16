# Maintainer: birdflesh <antkoul at gmail dot com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=libkgapi
pkgver=0.4.1
pkgrel=1
pkgdesc="A KDE-based library for accessing various Google services via their public API"
url='https://projects.kde.org/projects/kdereview/libkgoogle'
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
depends=('kdepimlibs' 'qjson')
makedepends=('cmake' 'automoc4' 'boost')
replaces=('libkgoogle')
conflicts=('libkgoogle')
source=("ftp://ftp.kde.org/pub/kde/stable/${pkgname}/${pkgver}/src/${pkgname}-${pkgver}.tar.bz2")
md5sums=('b4cefa643e95f5670997b5001547988f')

build() {
  cd "${srcdir}"
  mkdir build
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "${srcdir}"/build
  make DESTDIR="${pkgdir}" install
}
