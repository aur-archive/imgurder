# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=imgurder
pkgname=imgurder
pkgver=1.0
pkgrel=2
pkgdesc="Uploader for Imgur"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-curl>=1.3.5' 'haskell-directory=1.0.1.1' 'haskell-haskell98=1.0.1.1' 'haskell-hxt>=8.3.2' 'haskell-hxt-xpath>=8.5.4')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('5144f109f593ebeda43761bd79833eca')
