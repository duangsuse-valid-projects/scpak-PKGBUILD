# Maintainer: Duangsuse <fedora-opensuse@outlook.com>
pkgname=scpak
pkgver=0.3.1
pkgrel=1
pkgdesc="scpak is a unpack/repack tool for survivalcraft pak format"
url="https://github.com/qnnnnez/scpak"
arch=('any')
license=('MIT')
depends=()
optdepends=()
makedepends=('git' 'cmake' 'make')
conflicts=()
replaces=()
backup=()
source=("git://github.com/qnnnnez/scpak.git#branch=master")
md5sums=(SKIP)

build() {
cd "${srcdir}/scpak"
msg "finished git clone. downloading submodule..."
git submodule update --init
msg "finished update submodule,running cmake..."
cmake CMakeList.txt  msg "running make..."
make
if [ $? == 0 ] then
    msg "Done.Packing package..."
else
    msg "Looks like something went wrong with scpak's master branch. Go to https://github.com/qnnnnez/scpak/issues"
fi
}

package() { 
cd "${srcdir}/scpak" 
install -Dm644 bin/scpak "$pkgdir/usr/share/bin/scpak"
}


# vim:set ts=2 sw=2 et:
