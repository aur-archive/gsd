# Contributor: Vlatko Kosturjak <kost@linux.hr>

pkgname=gsd
pkgver=1.2.2
pkgrel=1
pkgdesc="Greenbone Security Desktop (gsd) - OpenVAS GUI frontend"
url="http://www.openvas.org/"
license=GPL
depends=('glibc' 'glib2' 'gnutls' 'openvas-libraries' 'qt' 'qtwebkit')
makedepends=('gcc' 'automake' 'cmake' 'doxygen')
backup=(etc/openvas/gsd_log.conf)
options=('!buildflags')
source=(http://wald.intevation.org/frs/download.php/1084/gsd-$pkgver.tar.gz gsd-enum-fix.patch)
md5sums=('12fcf80fc377e2d13c715d8162489e79' 'b5069fbede143de008c1b5a10e33e29c')
arch=('i686' 'x86_64')


build() {
  cd $startdir/src/$pkgname-$pkgver/

  patch -p1 < "$startdir/src/gsd-enum-fix.patch"

  cmake -DCMAKE_INSTALL_PREFIX=/usr -DSYSCONFDIR=/etc -DLOCALSTATEDIR=/var .
  make
  make DESTDIR="$pkgdir/" install
}
