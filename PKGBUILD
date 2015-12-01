pkgname=tesseract-ocr
pkgver=3.04.00
pkgrel=1
pkgdesc="Open Source OCR Engine"
arch=('x86_64')
url="https://github.com/${pkgname}"
license=('Apache 2.0')
depends=('leptonica' 'libpng12' 'libtiff' 'giflib' 'gcc-libs')
makedepends=('libtool' 'autoconf' 'automake')
optdepends=('tesseract-data-eng=3.04.00')
groups=('tesseract')
install=${pkgname}.install
source=("${pkgname}-${pkgver}::https://github.com/${pkgname}/tesseract/archive/${pkgver}.tar.gz"
)
sha512sums=('60c31bad40b4c01395782fb98b3326407e75ebdbda962de4fb0e878824efb05140bdcb139dcf7d4f699ae5350e81a00320ebe7fbec083a0d374952488cc59e25')

build() {
        cd "${srcdir}/${pkgname}-${pkgver}"
        ./autogen.sh
        ./configure --prefix=/usr
        make
}

package() {
        cd "${srcdir}/${pkgname}-${pkgver}"
        make DESTDIR="$pkgdir/" install
}
