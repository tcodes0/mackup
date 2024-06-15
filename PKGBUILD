# Maintainer: Raphael "Thom" Thomazella <thom atgolang dotdev dotbr>

pkgname=mackup-fork
pkgver=0def08b_20240615
pkgrel=1
pkgdesc="a small Python utitlity to keep your application settings in sync."
arch=('any')
url="https://github.com/tcodes0/mackup"
license=('GPL3')

depends=('python' 'python-docopt')
makedepends=('python' 'python-setuptools')
provides=('mackup')
conflicts=('mackup')

source=("git+https://github.com/tcodes0/mackup.git")
md5sums=('SKIP')

pkgver() {
  # cd "${pkgname%-git}"
  # git describe --always --tags | sed 's|-|.|g'
  echo $pkgver
}

package() {
  set -e
  \cd .pkgbuild
  git clone "${source[0]}" repo
  \cd repo
  python setup.py install --prefix=/usr --root="$pkgdir/" --optimize=1
  \cd ..
  \rm -fr repo
}
