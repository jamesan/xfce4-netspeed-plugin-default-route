# Maintainer: kfgz <kfgz at interia dot pl>
# Maintainer: Vinycius Maia <suportevg at uol dot com dot br>
# Contributor: James An <james@jamesan.ca>

pkgname=xfce4-netspeed-plugin-default-route
_pkgname=${pkgname%-default-route}
pkgver=0.3.1
pkgrel=1
pkgdesc="Netspeed plugin for xfce4 panel. Like gnome netspeed applet. Uses default route
as first choice for automatic selection"
arch=('i686' 'x86_64')
url="http://code.google.com/p/$_pkgname"
license=('GPL')
depends=('xfce4-panel' 'libxfcegui4' 'libgtop')
makedepends=('intltool')
provides=("$_pkgname=$pkgver")
conflicts=("$_pkgname")
replaces=("$_pkgname")
install=$_pkgname.install
source=("http://$_pkgname.googlecode.com/files/$_pkgname-$pkgver.tar.gz"
        default-route.patch)
md5sums=('b88cacc3ecd53798d76855e35a7a4d79'
         '7c9fb6fc30af1613019c5ee1c7ab177d')

prepare() {
  cd $_pkgname
  patch -i ../default-route.patch -p5
}

build() {
  cd $_pkgname
  ./configure --prefix=/usr
  make
}

package(){
  cd $_pkgname
  make DESTDIR=$pkgdir install
}
