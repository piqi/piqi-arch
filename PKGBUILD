# Original PKGBUILD by Taylor Venable <taylor@metasyntax.net>

pkgname=piqi-git
pkgver=20140401
pkgrel=1
pkgdesc='Universal schema language for JSON, XML, Protocol Buffers'
arch=('i686' 'x86_64')
url='http://piqi.org/'
license=('Apache')
makedepends=('git' 'ocaml' 'ocaml-findlib' 'pandoc')
provides=('piqi')
conflicts=('piqi')
options=('!strip' '!makeflags' 'docs')

_gitroot='git://github.com/alavrik/piqi.git'
_gitname='piqi'

build() {
  cd $srcdir

  if [[ -d $srcdir/$_gitname ]]; then
    cd $_gitname && git pull origin
  else
    git clone --depth=1 $_gitroot
    cd $_gitname
  fi

  git clean -ffdx

  export OCAMLPATH=
  ./configure --prefix="/usr"

  make deps
  make
  make doc
}

_docdir=/usr/share/doc/piqi/

package() {
  cd $_gitname
  make install DESTDIR="$pkgdir"
  install -d $pkgdir/$_docdir
  install -m 644 -t $pkgdir/$_docdir \
        doc/*.html
}
