# Maintainer: Yoel Lion <yoel3ster at gmail dot com>

pkgname=orayta-books-svn
pkgver=638
pkgrel=1
pkgdesc="Orayta books"
arch=('any')
license=('CC-BY-3.0')
url="http://code.google.com/p/orayta/"
depends=('orayta-svn')
makedepends=('subversion')
_svntrunk=http://orayta.googlecode.com/svn/books/
_svnmod=Books
build() {
  if [[ -d "$_svnmod/.svn" ]]; then
    (cd "$_svnmod" && svn up -r "$pkgver")
  else
svn co $_svntrunk $_svnmod
fi
  msg "SVN checkout done or server timeout"
  msg "Starting make..."
cd $_svnmod
./GenMakeFile.sh
make DESTDIR=$pkgdir install
}
