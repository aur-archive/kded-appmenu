pkgname=kded-appmenu
pkgver=0.9.20
pkgrel=1
pkgdesc="kded module that exports applications menu through dbus"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kdereview/kded-appmenu'
license=('GPL')
depends=('libdbusmenu-qt' 'kdelibs')
makedepends=('cmake' 'automoc4')
conflicts=('kded-appmenu-git')
source=("http://kde-apps.org/CONTENT/content-files/153882-kded-appmenu-$pkgver.tar.gz")
sha1sums=('3ac2db9a925a16391f5e9e5a7ee42d69e2e74b4b')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  rm -fr build
  mkdir build
  cd build
  cmake .. -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix`
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}/build"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
