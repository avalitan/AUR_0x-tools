# Maintainer: Avalitan <avalitan@avalitan.com>

pkgname=0x-tools
pkgver=v1.1.3
pkgrel=1
pkgdesc="Always-on Profiling for Production Systems"
arch=('x86_64')
url="https://0x.tools/"
license=('GPL2')
depends=()
makedepends=('git')
provides=('xcapture' 'psn')
source=("git+https://github.com/tanelpoder/0xtools.git")
sha256sums=('SKIP')

build() {
    cd "$srcdir/0xtools"
    git checkout tags/${pkgver}
    make
}

package() {
    cd "$srcdir/0xtools"
    mkdir -p "$pkgdir/usr/lib"
    mkdir -p "$pkgdir/usr/bin"
    PREFIX="$pkgdir/usr" make install
}

pkgver() {
    cd "$srcdir/0xtools"
    printf '%s' "$(git tag --sort=committerdate | tail -n1)"
}
