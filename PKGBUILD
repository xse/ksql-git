# Maintainer: xse <elouan.pignet@gmail.com>
pkgname=ksql-git
_pkgname=${pkgname%-*}
pkgver=0.2.5.3.gef0c422
pkgrel=1
pkgdesc="Yet another SQLite wrapper"
arch=("i686" "x86_64" "arm" "armv6h" "armv7h" "aarch64")
url="http://kristaps.bsd.lv/ksql/"
license=("custom:ISC") # included in source
depends=("sqlite")
makedepends=("git")
source=("git+https://github.com/kristapsdz/ksql.git")
sha512sums=("SKIP")

pkgver() {
  cd "$_pkgname"
  git describe --long --tags | sed 's/^VERSION_//;s/-/./g;s/_/./g'
}

build() {
  cd "$_pkgname"
  ./configure PREFIX="$pkgdir/usr" BINDIR="$pkgdir/usr/bin" SHAREDIR="$pkgdir/usr/share" SBINDIR="$pkgdir/usr/bin"  INCLUDEDIR="$pkgdir/usr/include" LIBDIR="$pkgdir/usr/lib" MANDIR="$pkgdir/usr/share/man"
  make
}

package() {
  cd "$_pkgname"
  make install
  install -Dm644 "LICENSE.md" "$pkgdir/usr/share/licenses/$_pkgname/LICENSE"
}
