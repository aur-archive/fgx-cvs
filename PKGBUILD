# Maintainer: Martynas Januskauskas <martynas@januskauskas.eu>
pkgname=fgx-cvs
pkgver=2.8.0
pkgrel=1
pkgdesc="** RENAMED TO fgx-git ** Launcher for free and open source FlightGear Flight Simulator, based on Qt (gitorious)"
arch=('x86_64' 'i686')
license=('GPL')
depends=('qt')
makedepends=('git' 'make' 'qt')
replaces=('fgx')
provides=('fgx')
conflicts=('fgx')
url="http://www.fgx.ch/"

build() {
	git clone http://git.fgx.ch/fgx
	cd $srcdir/fgx/src
	qmake && make

	echo "[Desktop Entry]
Type=Application
Name=FGx FlightGear Launcher
GenericName=FGx FlightGear Launcher
Comment=
Exec=fgx
Icon=fgx
Categories=Game;Simulation;" > ${srcdir}/fgx.desktop
}

package() {
	install -m655 -D "${srcdir}/fgx/src/fgx" "${pkgdir}/usr/bin/fgx"
	install -m644 -D "${srcdir}/fgx/src/resources/icons/fgx-logo-flyeronly.png" "${pkgdir}/usr/share/pixmaps/fgx.png"
	install -m644 -D "${srcdir}/fgx.desktop" "${pkgdir}/usr/share/applications/fgx.desktop"
}
