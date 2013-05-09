# Maintainer: Bill Durr <billyburly@gmail.com>
pkgname=ec2drv-git
_gitname=ec2
pkgver=0
pkgrel=1 
pkgdesc="Silicon Labritories EC2 jtag adapter linux driver"
url=""
arch=('i686' 'x86_64')
license=('GPL')
depends=('boost-libs'
         'python2')
makedepends=('boost')
provides=('ec2drv')
source=(git://github.com/billyburly/ec2.git)
md5sums=('SKIP')

pkgver() {
  cd $srcdir/$_gitname
  git describe --always | sed 's|-|.|g'
}

build() {
  cd $srcdir/$_gitname
  mkdir m4
  autoreconf -i
  ./configure --prefix=/usr
  make
}

package() {
  cd $srcdir/$_gitname
  find "$pkgdir" -type d -name .git -exec rm -r '{}' +
  make DESTDIR="$pkgdir" install
}
