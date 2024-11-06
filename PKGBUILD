pkgname=dotmng
pkgver=1.1
pkgrel=1
pkgdesc="A dotfile management script for Arch-based systems."
arch=('any')
url="https://github.com/jotalevi/.mng"
license=('MIT')
depends=('git' 'rsync' 'pacman')
source=("$pkgname-$pkgver.tar.gz::https://github.com/jotalevi/.mng/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('SKIP')

package() {
    install -Dm755 "$srcdir/.mng-$pkgver/dotmng" "$pkgdir/usr/bin/.mng"
}
