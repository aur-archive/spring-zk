# Contributor: NiteHogg <keith.b.elliott [at] gmail [dot] com>

pkgname=spring-zk
pkgver=1.3.4.2
pkgrel=1
pkgdesc="Zero-K is a free, multiplatform, open-source RTS game"
arch=(any)
url="http://zero-k.info/"
license=('GPL')
depends=('spring')
makedepends=('git' 'zip')
source=(git+https://github.com/ZeroK-RTS/Zero-K.git#commit=86edcf9)
md5sums=('SKIP')

prepare() {
  cd "$srcdir"/Zero-K
  sed -i "s|\$VERSION|${pkgver}|g" modinfo.lua
}

build() {
  cd "$srcdir"/Zero-K
  zip -qr zk-v${pkgver}.sdz *
}

package() {
  cd "$srcdir"/Zero-K
  install -d "$pkgdir"/usr/share/spring/games
  install -Dm644 zk-v${pkgver}.sdz "$pkgdir"/usr/share/spring/games
}

