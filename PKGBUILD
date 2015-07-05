# Contributor: Adria Arrufat <swiftscythe @t gmail d@t com>
# Contributor: Gordin <9ordin @t gmail d@t com>

pkgname=screenkey
pkgver=0.2
pkgrel=6
pkgdesc="Screencast tool to show your keys inspired by Screenflick, based on key-mon."
arch=('any')
url="http://launchpad.net/screenkey"
license=('GPL3')
depends=('pygtk' 'python2-xlib' 'xorg-xmodmap')
makedepends=('python2-distutils-extra' 'python2-setuptools')
source=("http://launchpad.net/$pkgname/$pkgver/$pkgver.0/+download/$pkgname-$pkgver.tar.gz")
sha1sums=('a775ad6f7ed2d63348a4fb9b4c7f193afbd2a062')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  # Fix hardcoded install path...
  sed -i "s|/usr/share/|share/|" setup.py
  sed -i "1s|env python|env python2|" Screenkey/modmap.py

  python2 setup.py build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  python2 setup.py install --skip-build --optimize=1 --prefix="$pkgdir/usr"
}

# vim:set ts=2 sw=2 et:
