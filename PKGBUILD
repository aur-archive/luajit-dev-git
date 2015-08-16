# Maintainer: Lulker <lulker@chome.ws>
pkgname=luajit-dev-git
_gitname=luajit-2.0
pkgver=20130603
pkgrel=1
pkgdesc="A Just-In-Time Compiler for Lua, development branch, builds amalgamated binary."
url="http://luajit.org"
arch=('x86_64' 'i686')
license=('MIT')
makedepends=('git')
provides=('luajit')
conflicts=('luajit')
source=('git+http://luajit.org/git/luajit-2.0.git#branch=v2.1')
md5sums=('SKIP')

pkgver() {
  date +%Y%m%d
}

package() {
  cd $_gitname
  make install PREFIX=/usr DESTDIR="$pkgdir"
  LUAJITBIN=`ls $pkgdir/usr/bin/luajit-* | sed "s|$pkgdir||"`
  ln -sf "$LUAJITBIN" $pkgdir/usr/bin/luajit
}

build() {
  cd $_gitname
  make amalg PREFIX=/usr
}