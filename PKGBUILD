# Maintainer: Moritz Maxeiner <moritz@ucworks.org>

pkgname=comp-scale
_gitname=comp-scale
pkgver=161.5099877
_commit=50998774aa35abdbda2d40e45dfac2183b33329c
pkgrel=1
pkgdesc="Enlightenment e17 module: Scale windows down to see them all. Side by side.  Git version for use with stable enlightenment17 release"
arch=('i686' 'x86_64')
url="http://git.enlightenment.org/enlightenment/modules/comp-scale.git/"
license=('MIT')
depends=('enlightenment17')
makedepends=('git')
provides=('comp-scale')
options=('!libtool')
source=()
conflicts=('e-modules-extra' 'comp-scale-git' 'comp-scale-svn')
source=("$_gitname::git://git.enlightenment.org/enlightenment/modules/comp-scale.git#commit=$_commit")
md5sums=('SKIP')

pkgver() {
  cd $_gitname
  # Use the tag of the last commit
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "$_gitname"
  ./autogen.sh --prefix=/usr
  make
}

package() {
  cd "$_gitname"
  make DESTDIR="$pkgdir/" install

  install -D -m644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING
  install -D -m644 COPYING-PLAIN $pkgdir/usr/share/licenses/$pkgname/COPYING-PLAIN
}
