# Contributor: Maciej Sitarz <macieks@freesco.pl>

pkgname=mythes-pl
pkgver=1.5
pkgrel=1
pkgdesc="Polish thesaurus"
arch=(any)
url="http://synonimy.ux.pl/"
license=('LGPL')
optdepends=('libmythes: offers thesaurus library functions')
source=(http://downloads.sourceforge.net/synonimy/OOo2-Thesaurus-${pkgver}.zip)
md5sums=('c5ff330768241baf2d61f15fbb9be1b9')

build() {
	/bin/true
}

package() {
  cd "$srcdir"
  install -dm755 ${pkgdir}/usr/share/mythes
  install -m644 th_pl_PL_v2.* $pkgdir/usr/share/mythes

  # the symlinks
  install -dm755 ${pkgdir}/usr/share/myspell/dicts
  pushd $pkgdir/usr/share/myspell/dicts
    for file in $pkgdir/usr/share/mythes/*; do
      ln -sv /usr/share/mythes/$(basename $file) .
    done
  popd
  
  # docs
  install -dm755 ${pkgdir}/usr/share/doc/$pkgname
  install -m644 README_th_pl_PL_v2.txt $pkgdir/usr/share/doc/$pkgname
}
