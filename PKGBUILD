# Maintainer: Todd Partridge <https://github.com/Gen2ly/archpkgs>

pkgname=genscripts-git
_pkgname=${pkgname%-*}
pkgver=1.20.0
pkgrel=1
pkgdesc="General utility scripts."
arch=("any")
url="https://github.com/Gen2ly/$_pkgname"
license=("GPL2")
depends=("bash")
makedepends=("git")
replaces=("genscripts")
install=
source=("git://github.com/Gen2ly/$_pkgname")
md5sums=('SKIP')

pkgver() {
  cd $srcdir/$_pkgname
  git describe --long | sed -r 's/-([0-9,a-g,A-G]{7}.*)//' | sed 's/-/./'
}

package() {
  cd $srcdir/$_pkgname
  install -Dm755 bckfile     $pkgdir/usr/bin/bckfile
  install -Dm755 bgcmd       $pkgdir/usr/bin/bgcmd
  install -Dm755 cbin        $pkgdir/usr/bin/cbin
  install -Dm755 cbout       $pkgdir/usr/bin/cbout
  install -Dm755 devtop      $pkgdir/usr/bin/devtop
  install -Dm755 dirsize     $pkgdir/usr/bin/dirsize
  install -Dm755 gurl        $pkgdir/usr/bin/gurl
  install -Dm755 largefiles  $pkgdir/usr/bin/largefiles
  install -Dm755 lnk         $pkgdir/usr/bin/lnk
  install -Dm755 memtop      $pkgdir/usr/bin/memtop
  install -Dm755 pack        $pkgdir/usr/bin/pack
  install -Dm755 pwr         $pkgdir/usr/bin/pwr
  install -Dm755 rps         $pkgdir/usr/bin/rps
  install -Dm755 screenshot  $pkgdir/usr/bin/screenshot
  install -Dm755 tock        $pkgdir/usr/bin/tock
  install -Dm755 tputcolors  $pkgdir/usr/bin/tputcolors
  install -Dm755 trsh        $pkgdir/usr/bin/trsh
  install -Dm755 turl        $pkgdir/usr/bin/turl
  install -Dm755 wordsort    $pkgdir/usr/bin/wordsort
  install -Dm755 unpack      $pkgdir/usr/bin/unpack
  install -Dm755 xtermcolors $pkgdir/usr/bin/xtermcolors
  install -Dm644 license.txt $pkgdir/usr/share/licenses/$_pkgname/license.txt

  install -d                 $pkgdir/usr/share/man/man1/
  pod2man --section=1 --center="$_pkgname manual" --name=$_pkgname \
    --release="$pkgver" readme.pod | \
    gzip > $pkgdir/usr/share/man/man1/${_pkgname}.1.gz
}

# vim:set ts=2 sw=2 et:
