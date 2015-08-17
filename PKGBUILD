# Maintainer: <kfgz at interia dot pl>

pkgname=tpc
pkgver=0.44rc2
pkgrel=2
pkgdesc="Tool for undervolting/overclocking Family 10h, 11h, 12h, 14h and 15h AMD processors."
arch=('i686' 'x86_64')
url="https://code.google.com/p/turionpowercontrol/"
license=('unknown')
depends=('gcc-libs' 'ncurses')
install=tpc.install
_pkgver="${pkgver:0:4}-${pkgver:4}"
source=(https://turionpowercontrol.googlecode.com/files/${pkgname}-${_pkgver}-src.tar.gz
        tpc.conf)
sha1sums=('bda793d1ce263e1e119ea8dc2a3556a07909b113'
          'da954dbece5ea85cbee4ec1fdf32f4e144b538d3')

build() {
  cd "${srcdir}"/${pkgname}-${_pkgver}-src
  make 
}

package() {
  install -Dm755 "${srcdir}"/${pkgname}-${_pkgver}-src/TurionPowerControl "${pkgdir}"/usr/bin/tpc
  install -Dm644 "${srcdir}"/tpc.conf "${pkgdir}"/etc/modules-load.d/tpc.conf 
}
