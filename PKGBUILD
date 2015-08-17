#Contributor: mathieu.clabaut <mathieu.clabaut@gmail.com>

pkgname=python2-pyocr-git
pkgver=20120912
pkgrel=2
pkgdesc="optical character recognition (OCR) tool wrapper for python."
arch=('i686' 'x86_64')
url="https://github.com/jflesch/pyocr"
license=('GPL2')
provides=('python2-pyocr')
conflicts=('python2-pyocr')
makedepends=('python2' 'python2-setuptools')
#depends=('python2-gtk2' 'python2-glade2' 'python2-pycountry' 'python2-imaging' 'python2-poppler' 'python2-pyinsane' 'python2-pyocr')
source=()
md5sums=()

_gitroot="git://github.com/jflesch/pyocr.git"
_gitrepo="pyocr"

build() {
  cd $srcdir

  if [ -d $_gitrepo ]; then
    (cd $_gitrepo && git pull -u origin)
  else
    git clone $_gitroot $_gitrepo
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting make..."

  [ -d $_gitrepo-build ] && rm -rf $_gitrepo-build 
  cp -r $_gitrepo $_gitrepo-build
  cd $_gitrepo-build
  python2 ./setup.py install --root=$pkgdir  || return 1


}

