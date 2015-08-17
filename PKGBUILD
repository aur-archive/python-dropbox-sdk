pkgname=python-dropbox-sdk
pkgver=2.1.0
pkgrel=2
pkgdesc="Python SDK for Dropbox Core APIs"
arch=('any')
url="https://www.dropbox.com/developers/core/sdks/python"
license=('custom:MIT')
depends=('python' 'python-urllib3')
makedepends=('python-setuptools')
source=("https://www.dropbox.com/developers/downloads/sdks/core/python/dropbox-python-sdk-$pkgver.zip")
sha1sums=('1ac6d601a4d0ce7085120c07fcf54cc98351359c')

build() {
  msg "Starting build"
  cd "$srcdir/dropbox-python-sdk-$pkgver"
  python setup.py build
}
package() {
  msg "Running setup"
  cd "$srcdir/dropbox-python-sdk-$pkgver"
  python setup.py install --root=${pkgdir} --optimize=1
  
  msg "Adding license file"
  licensedir=$pkgdir/usr/share/licenses/$pkgname/
  install -d $licensedir
  cp -ra $srcdir/dropbox-python-sdk-$pkgver/LICENSE* $licensedir
}
