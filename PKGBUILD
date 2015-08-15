# Mainteiner: Fabio Melo Pfeifer <fmpfeifer@gmail.com> 

pkgname=bulk_extractor-new
_pkgname=bulk_extractor
pkgver=1.5.5
pkgrel=3
pkgdesc="Bulk Email and URL extraction tool"
arch=('i686' 'x86_64')
url="http://afflib.org"
license=('GPL')
depends=('tre' 'java-environment' 'liblightgrep>=1.4.0' 'ttf-dejavu')
optdepends=('libewf: for reading EnCase E01 evidence files'
            'afflib: for reading AFF evidence files'
            'exiv2: for decoding JPEG Exifs'
            'openssl: for crypto primitives')
provides=('bulk_extractor')
conflicts=('bulk_extractor')

source=(http://digitalcorpora.org/downloads/bulk_extractor/${_pkgname}-${pkgver}.tar.gz)
sha1sums=('59cab1d96089043ad4a74483bd09179262b136ab')

build() {
	cd $srcdir/$_pkgname-$pkgver
	./configure --prefix=/usr --sysconfdir=/etc --enable-lightgrep
	make || return 1
}

package() {
        cd $srcdir/$_pkgname-$pkgver
        make DESTDIR=$pkgdir install || return 1
}
