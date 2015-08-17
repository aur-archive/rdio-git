# Maintainer: Mike Cooper <mythmon@gmail.com>
pkgname=rdio-git
pkgver=r43.5ccf271
epoch=1
pkgrel=2
pkgdesc="Standalone webview for Rdio music service."
arch=('i686' 'x86_64')
url="https://github.com/sgringwe/rdio"
license=('GPL')
depends=(
    'webkitgtk'
    'libnotify'
    'desktop-file-utils'
)
makedepends=('git' 'cmake' 'vala>=0.17.5')
install=rdio-git.install
conflicts=('rdio')
provides=('rdio')
source=("$pkgname"::'git+https://github.com/sgringwe/rdio.git')
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "$srcdir/$pkgname"
    cmake -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "$srcdir/$pkgname"
    make PREFIX=/usr DESTDIR="$pkgdir" install
}
