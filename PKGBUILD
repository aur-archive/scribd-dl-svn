# Maintainer: Maxwell Pray a.k.a. Synthead <synthead@gmail.com>

pkgname=scribd-dl-svn
pkgver=20120624
pkgrel=1
pkgdesc="Script to download books from scribd"
arch=('any')
url="https://github.com/synthead/scribd-dl"
license=('GPL')
depends=('wget' 'imagemagick' 'pdftk')
makedepends=('git')

_gitroot=https://github.com/synthead/scribd-dl.git
_gitname=scribd-dl

package() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
  msg "Starting build..."

  install -Dm 755 "$srcdir/$_gitname/scribd-dl" "$pkgdir/usr/bin/scribd-dl"
}
