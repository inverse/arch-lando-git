# Maintainer: Malachi Soord <me@malachisoord.com>
pkgname=lando
pkgver=3.0.0.beta.37
_realver=3.0.0-beta.37
pkgrel=1
pkgdesc="Lando is for developers who want to quickly specify and painlessly spin up the services and tools needed to develop their projects."
url="https://docs.devwithlando.io"
arch=('x86_64')
license=('GPL3')
depends=('npm yarn docker')

source=("https://github.com/lando/lando/archive/v$_realver.tar.gz")
sha256sums=('7d02ea87478841b643b57b6cbbb88d0163c20d76ea2bd2c99593662418d81175')

build() {
    cd "$pkgname-$_realver"
    yarn
    npm run pkg:cli
}

package() {

  cd "$pkgname-$_realver"

  install -D -m 744 "dist/cli/lando-linux-x64-v$_realver" "{pkgdir}/usr/bin/lando"

  # Install licence
  install -D -m 644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  # Install Readme
  install -D -m 644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}
