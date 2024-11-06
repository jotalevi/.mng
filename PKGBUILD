# Maintainer: Jotalevi <youremail@example.com>
pkgname=.mng
pkgver=1.0
pkgrel=1
pkgdesc="A script to manage dotfiles with various functions and Git tracking"
arch=('any')
url="https://github.com/jotalevi/.mng"  # Link to your GitHub repo
license=('MIT')  # Adjust to your script's license if different
depends=('git' 'rsync' 'pacman')
source=("$pkgname-$pkgver.tar.gz::https://github.com/jotalevi/.mng/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('SKIP')  # Replace with actual checksum if known

package() {
    install -Dm755 "$srcdir/.mng-$pkgver/.mng.sh" "$pkgdir/usr/bin/.mng"
}
