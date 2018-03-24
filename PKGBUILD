# Maintainer: Malachi Soord <me@malachisoord.com>
pkgname=lando
pkgver=v3.0.0.beta.36.r201.gb62391ec
pkgrel=1
pkgdesc="Lando is for developers who want to quickly specify and painlessly spin up the services and tools needed to develop their projects."
arch=('any')
license=('GPL3')
depends=('npm yarn')

source=("$pkgname::git+https://github.com/lando/lando.git")
sha256sums=('SKIP')

pkgver() {
  cd "$pkgname"
  git describe --long | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
    cd "$pkgname"
    npm run pkg:cli
}

package() {
  cd "$pkgname"
  install -D -m 644 LICENSE.md ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}
