pkgname=sir
pkgver=2.8
pkgrel=1
pkgdesc="Simple image resizer in Qt" 
arch=('x86_64')
url="http://marek629.github.io/SIR/" 
license=('GPLv2') 
depends=('qt5-base' 'qt5-svg' 'exiv2')
makedepends=('qt5-tools' 'cmake')
optdepends=("dcraw: RAW images support")
source=("https://github.com/marek629/SIR/archive/v${pkgver}.tar.gz") 
sha512sums=('e568d31746d7eb24d6ab90e4c14a19e2a014ddeab2fcc3a4fa0853b72487a1a05d1b79abac20a5a2cbca252f09f5f7d0a08e578b101a153d825076370730406f')

build() {
     cd "$srcdir/SIR-${pkgver}"
     [ -d build ] || mkdir build && cd build
     cmake .. -DCMAKE_INSTALL_PREFIX=/usr \
              -Dmetadata=ON -Dqt5=ON
     make sir
}

package() {
     cd "$srcdir/SIR-${pkgver}/build"
     make DESTDIR="$pkgdir/" install
}  
