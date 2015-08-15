# Maintainer: Bastien Dejean <baskerville@lavabit.com>

_pkgname=dzen
pkgname=${_pkgname}2-bskv-git
pkgver=10
pkgrel=1
pkgdesc='General purpose messaging, notification and menuing program for X'
arch=('i686' 'x86_64')
url='https://github.com/robm/dzen'
license=('custom:MIT')
depends=('libxft')
makedepends=('git')
provides=("${_pkgname}2")
conflicts=("${_pkgname}2")
source=('git://github.com/robm/dzen.git')
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/$_pkgname"
    git rev-list --count HEAD
}

build() {
    cd "$srcdir/$_pkgname"
    make PREFIX=/usr
}

package() {
    cd "$srcdir/$_pkgname"
    make PREFIX=/usr DESTDIR="$pkgdir" install
    install -D -m644 README "$pkgdir/usr/share/doc/$pkgname/README"
    install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
