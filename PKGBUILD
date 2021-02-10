# Maintainer: Felix Fung <fylixeoi@gmail.com>
# Maintainer: Loïc Tosser <loic@kalvad.com>

pkgname=timescaledb
pkgver=2.0.1
pkgrel=0
pkgdesc="An open-source time-series database optimized for fast ingest and complex queries."
arch=('i686' 'x86_64')
url="http://www.timescale.com/"
license=('Apache')
depends=('postgresql-12' 'postgresql-libs-12')
makedepends=('gcc' 'cmake>=3.4' 'git')
install=${pkgname}.install
source=("https://github.com/timescale/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=("96e51d5240547f0223c34b91263f6fffca46927710764bf450aa61e9756189bd")

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./bootstrap -DWARNINGS_AS_ERRORS=OFF -DREGRESS_CHECKS=OFF
    cd build && make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}/build"
    make DESTDIR="$pkgdir/" install
}
